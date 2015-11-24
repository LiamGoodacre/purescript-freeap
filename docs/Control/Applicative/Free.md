## Module Control.Applicative.Free

#### `FreeAp`

``` purescript
data FreeAp f a
```

The free applicative functor for a type constructor `f`.

##### Instances
``` purescript
instance functorFreeAp :: Functor (FreeAp f)
instance applyFreeAp :: Apply (FreeAp f)
instance applicativeFreeAp :: Applicative (FreeAp f)
```

#### `NaturalTransformation`

``` purescript
type NaturalTransformation f g = forall a. f a -> g a
```

#### `liftFreeAp`

``` purescript
liftFreeAp :: forall f a. f a -> FreeAp f a
```

Lift a value described by the type constructor `f` into
the free applicative functor.

#### `retractFreeAp`

``` purescript
retractFreeAp :: forall f a. (Applicative f) => FreeAp f a -> f a
```

Run a free applicative functor using the applicative instance for
the type constructor `f`.

#### `foldFreeAp`

``` purescript
foldFreeAp :: forall f g a. (Applicative g) => NaturalTransformation f g -> FreeAp f a -> g a
```

Run a free applicative functor with a natural transformation from
the type constructor `f` to the applicative functor `g`.

#### `hoistFreeAp`

``` purescript
hoistFreeAp :: forall f g a. NaturalTransformation f g -> FreeAp f a -> FreeAp g a
```

Natural transformation from `FreeAp f a` to `FreeAp g a` given a
natural transformation from `f` to `g`.

#### `analyzeFreeAp`

``` purescript
analyzeFreeAp :: forall f m a. (Monoid m) => (forall b. f b -> m) -> FreeAp f a -> m
```

Perform monoidal analysis over the free applicative functor `f`.


