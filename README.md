# Tutoriel Rust

## Variables et mutabilité

En Rust, une variable est une valeur que vous pouvez accrocher à un nom pour la réutiliser dans votre code. Par défaut, une fois qu'une variable est déclarée en Rust, elle ne peut pas être modifiée. Cependant, vous pouvez utiliser le mot-clé `mut` pour rendre une variable mutable, c'est-à-dire qu'elle peut être modifiée après sa déclaration.

```rust
let mut foo = 10;
foo = 20; // Ceci est autorisé car foo est mutable
```

## Constantes

Les constantes en Rust sont déclarées avec le mot-clé `const` et ne peuvent pas être modifiées une fois déclarées. Contrairement aux variables, vous devez spécifier le type de la constante lors de sa déclaration.

```rust
const FOO_BAR: i32 = 10;
println!("La valeur de FOO_BAR est {}", FOO_BAR);
```

## Shadowing

Le shadowing est une autre façon de réassigner une variable en Rust. Avec le shadowing, vous pouvez déclarer une nouvelle variable avec le même nom qu'une variable existante, ce qui "masque" la variable originale. Le shadowing est différent de la mutabilité en ce sens qu'il crée une nouvelle variable à chaque fois, ce qui signifie que le type de la variable peut changer.

```rust
let bar = 10;
let bar = bar + 1; // Ceci est autorisé et crée une nouvelle variable bar
println!("La valeur de bar après shadowing est {}", bar);
```

## Scope

Le scope d'une variable se réfère à la partie du code où une variable est accessible. En Rust, le scope d'une variable est déterminé par le bloc de code dans lequel elle est déclarée. Une fois que vous sortez de ce bloc de code, la variable n'est plus accessible.

```rust
let bar = 11;
{
    let bar = 5; // Ceci crée une nouvelle variable bar qui n'est accessible qu'à l'intérieur de ce bloc de code
    println!("La valeur de bar à l'intérieur du scope est {}", bar);
}
println!("La valeur de bar à l'extérieur du scope est {}", bar);
```

## Les paramètres additionnels

En Rust, vous pouvez utiliser des paramètres additionnels pour formater vos chaînes de caractères. C'est particulièrement utile lorsque vous voulez insérer des valeurs variables dans une chaîne de caractères, comme lors de l'utilisation de la macro println!.

### Utilisation de base

Pour utiliser des paramètres additionnels, vous utilisez des accolades {} dans votre chaîne de caractères, puis vous fournissez les valeurs à insérer après la chaîne de caractères.

```rust
let x = 10;
let y = 5;
println!("{} + {} = {}", x, y, x + y);
```

Dans cet exemple, les accolades {} sont remplacées par les valeurs de x, y, et x + y dans l'ordre.

### Arguments positionnels

Vous pouvez également utiliser des arguments positionnels pour réutiliser les mêmes valeurs plusieurs fois ou pour les utiliser dans un ordre différent.

```rust
let x = 10;
let y = 5;
println!("{0} + {1} = {2}, {0} - {1} = {3}", x, y, x + y, x - y);
```

Dans cet exemple, {0} est remplacé par la première valeur (ici x), {1} est remplacé par la deuxième valeur (ici y), {2} est remplacé par la troisième valeur (ici x + y), et {3} est remplacé par la quatrième valeur (ici x - y).

### Erreurs courantes

Si vous oubliez de fournir une valeur pour un paramètre additionnel, vous obtiendrez une erreur de compilation.

```rust
let x = 10;
let y = 5;
println!("{} + {} = {}", x, y); // Erreur : argument jamais utilisé
```

De même, si vous fournissez plus de valeurs que nécessaire, vous obtiendrez également une erreur de compilation.

```rust
let x = 10;
let y = 5;
println!("{} + {}", x, y, x + y); // Erreur : argument positionnel inutilisé
```

## Les types de données

### Les nombres entiers

En Rust, vous pouvez avoir des nombres entiers de différentes tailles et signes. Par exemple, vous pouvez avoir des nombres entiers signés de 8 bits (i8), de 16 bits (i16), de 32 bits (i32), de 64 bits (i64), et de 128 bits (i128). Les nombres entiers signés peuvent être positifs ou négatifs.

Vous pouvez également avoir des nombres entiers non signés, qui ne peuvent être que positifs. Ces types sont indiqués par un u au lieu d'un i, comme u8, u16, u32, u64, et u128.

```rust
let x: i16 = 10;
let y: u16 = 5;
println!("{} - {} = {}", x, y, x - y as i16);
```

### Les nombres à virgule flottante

Les nombres à virgule flottante en Rust peuvent être de deux types : f32 et f64. Ces types représentent des nombres à virgule flottante de 32 bits et de 64 bits respectivement. Par défaut, Rust utilise f64 car il offre plus de précision.

```rust
let x: f32 = 2.5;
let y: f64 = 10.0;
println!("{} - {} = {}", x, y, x - y as f32);
```

### Les booléens

Les booléens en Rust sont représentés par le type bool. Ils peuvent avoir deux valeurs : true ou false.

```rust
let x: bool = true;
println!("La valeur de x est {}", x);
```

### Les caractères

```rust
let x: char = 'z';
println!("La valeur de x est {}", x);
```

```rust

```
