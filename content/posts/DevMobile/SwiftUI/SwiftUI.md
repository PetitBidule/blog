## Struct SwiftUI

Struct et l'équivalent des class en swift.

Struct est basée sur le type de valeur ce qui est donc plus avantageux pour suivre les modifications des données que Class.
En termes de performances Struct est plus rapide et plus simple que Class.

## Some SwiftUI

some représente un type opaque // a revoir

## protocole 

Les protocoles sont un moyen de décrire les propriétés et les méthodes que quelques choses doit avoir.

Exemple:
```swift
protocol Identifiable {
    var id: String { get set }
}
```
Dans cet exemple le protocole Identifiable permet d'attribuer un id à chaque type conformes. Cet id pourra ensuite etre lu en utilisant get ou set.



