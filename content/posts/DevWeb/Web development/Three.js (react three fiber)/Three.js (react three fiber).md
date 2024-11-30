# React three fiber

Three.js est une puissante bibliothèques open-source qui permet de créer de superbes model 3D dans le web  
Avec three.js, nous pouvons créer des géométries complexes, des effets d'éclairages et d'ombres réaliste.

## Structure d'une application three.js

![2e484eb97f8b52e9a8aab187f3aa2679.png](../../_resources/2e484eb97f8b52e9a8aab187f3aa2679.png)

## Base three.js

- Moteur de rendu: Le moteur de rendu est responsable du dessin de la scène 3d sur la page web.  
    (Il utilise WebGL\*\*, une api graphique basée sur OpenGL Es, pour intéragir avec le GPU et dessiner la scène sur la page web.)  
    \*\*WebGL (Web Graphics Library) == api javascript permettan le rendu de graphismes en 2D ou 3D avec de hautes performances, sans avoir à utiliser de plugin.
    
- Geometrie: La géométrie définit la forme et la structure d'un objet. Elle composée de sommets et faces.
    
- Lumière: L'éclairage est utilisé pour simuler la façon dont la lumière intéragit avec les objets de la scène. Les lumières sont utilisées pour éclairer la scène et créer des zones d'ombres
    
- Caméra: La caméra détermine la perspective et la position du spectateur dans la scène.
    
- Le matériau: Définit l'apparence d'un objet dans la scène, y compris sa couleur, sa texture, et son ombrage. Les matériaux sont appliqués aux géométries pour définir leur apparence.
    
- Scene: La scène est le conteneur qui contient tous les objets, les lumières et les caméras dans three.js
    
- Texture: Imaga appliquée à un méteriau.
    
- Animation: Création d'un mouvement ou d'un changement dans une scene 3D au fil du temps.
    

## React Three FIber

React Three Fiber est une librairie qui simplifie la construction d'application 3D avec Three.js et React.  
Tout ce qui fonctionne dans Three.js fonctionnera avec React Three Fiber

Install React three Fiber:

```shell
npm install three @types/three @react-three/fiber
```

Exemple:

```React
import React, { Suspense } from 'react'
import { Canvas, useLoader } from '@react-three/fiber'
import Loader from '../components/Loader'
import Island from '../model/islands3D'
import { Octahedron, OrbitControls } from '@react-three/drei'

const Home = () => {
  return (
    <>
    <section className='w-full h-screen'>
       <Canvas> // permet de créer la scène, la caméra et le moteur de rendu. 
                 <mesh> //objet de scène utilisée pour contenir la géométrie et le matériau.
                  <ambientLight intensity={0.5}/> // éclaire globalement tous les objets de la scène de manière égale.
                  <directionalLight/> // lumière émise dans une direction spécifique 
                  <boxGeometry args={[2, 5, 2]}/>
				   					// permet de créer un cuboide rectangulaire
                  2: largeur, 5: hauteur, 2: profondeur
                  <meshNormalMaterial/>
                 </mesh>
             </Canvas> 
    </section>
    </>
  )
}

export default Home

```

![a3ea48387c6d64110e3333b408a0956f.png](../../_resources/a3ea48387c6d64110e3333b408a0956f.png)