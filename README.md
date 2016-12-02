# PackageFactory.AtomicFusion

> Prototypes that help implementing atomic-design and a component-architecture in Neos.Fusion

## Usage 

```
prototype(Vendor.Site:Component) < prototype(PackageFactory.AtomicFusion:Component) {
    
    #
    # all fusion properties except renderer are evaluated and passed 
    # are made available to the renderer as object ``props`` in the context
    # 
    title = ''
    description = ''

    #
    # the renderer path is evaluated with the props in the context
    # that way regardless off nesting the props can be accessed
    # easily via ${props.__name__}
    # 
    renderer = TYPO3.TypoScript:Tag {
        content = TYPO3.TypoScript:Array {
            headline = TYPO3.TypoScript:Tag {
                tagName = 'h1'
                content = ${props.title}
            }

            description = TYPO3.TypoScript:Tag {
                tagName = 'p'
                content = ${props.description}
            }
      }
}
```
