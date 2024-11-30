Install Custom Ui Router App forge

créer une app classique ensuite  
le manifest doit ressembler à ceci:  
(je rajouterai ensuite les scopes pour les api etc, )

![Capture d'écran 2024-05-03 130419.png](../_resources/Capture%20d_écran%202024-05-03%20130419.png)

ensuite

accedes au **static/** répertoire, `npm install react-router`, puis `npm install @forge/bridge@latest`, après dans le **src/App.js** et coller ce code que j'ai repris de la doc et que j'ai intéger à mon app, avant de faire ceci créer les différents dossier pour les view.

Exemple:

![Capture d'écran 2024-05-03 131248.png](../_resources/Capture%20d_écran%202024-05-03%20131248.png)

```js
import React, { Fragment, useEffect, useState } from "react";
import { view } from "@forge/bridge";
import { Router, Route, Routes, useNavigate } from "react-router";
import PiPlanningView from "./Pi-Planning/PiPlanningView";
import TeamBreakoutsView from "./TeamBreakouts/TeamBreakoutsView";

function Link({ to, children }) {
  const navigate = useNavigate();
  return (
    <a
      href={to}
      onClick={(event) => {
        event.preventDefault();
        navigate(to);
      }}
    >
      {children}
    </a>
  );
}

function Home() {
  return (
    <Fragment>
      <h2>Home</h2>
      <Link to="/page-with-path">Route to page with path</Link>
    </Fragment>
  );
}

function PageWithPath() {
  return <h2>Page with path</h2>;
}

function App() {
  const [history, setHistory] = useState(null);

  useEffect(() => {
    view.createHistory().then((newHistory) => {
      setHistory(newHistory);
    });
  }, []);

  const [historyState, setHistoryState] = useState(null);

  useEffect(() => {
    if (!historyState && history) {
      setHistoryState({
        action: history.action,
        location: history.location,
      });
    }
  }, [history, historyState]);

  useEffect(() => {
    if (history) {
      history.listen((location, action) => {
        setHistoryState({
          action,
          location,
        });
      });
    }
  }, [history]);

  return (
    <div>
      {history && historyState ? (
        <Router
          navigator={history}
          navigationType={historyState.action}
          location={historyState.location}
        >
          <Routes>
            <Route
              path="/TeamBreakouts"
              element={<TeamBreakoutsView />}
            ></Route>
            <Route path="/Pi-Planning" element={<PiPlanningView />}></Route>
            <Route path="/" element={<Home />}></Route>
          </Routes>
        </Router>
      ) : (
        "Loading..."
      )}
    </div>
  );
}

export default App;

```

voila normalement c'est bon, j'ajouterai dpc typescript etc.  
si besoin d'aide:  
 [Ajouter un routage à une application pleine page d'interface utilisateur personnalisée](https://developer.atlassian.com/platform/forge/add-routing-to-a-full-page-app/#create-a-custom-ui-jira-admin-page-app).


modules:
  jira:projectPage:
    - key: jira-pi-planning
      resource: main
      resolver:
        function: resolver
      title: Team Breakout
  function:
    - key: resolver
      handler: index.handler
resources:
  - key: main
    path: static/pi-planning/build
    tunnel:
      port: 3000
permissions:
  content:
    styles:
      - unsafe-inline
  scopes:
    - read:jira-user
    - read:board-scope:jira-software
    - read:project:jira
    - read:sprint:jira-software
    - read:issue-details:jira
    - read:epic:jira-software
    - read:jql:jira
    - read:jira-work
app:
  id: ari:cloud:ecosystem::app/44e2e185-771f-4e53-a563-6e659824cb3b
  
 