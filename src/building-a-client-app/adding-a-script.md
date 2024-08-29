# Adding a script

MXML files insert ActionScript code through a `<sw:Script>` tag containing code inside a `<![CDATA[ ... ]]>` markup.

```mxml
<!-- src/com/example/ExampleApplication.mxml -->
<?xml version="1.0"?>
<sw:Application xmlns:sw="http://ns.skywhack.net/2024">
    <sw:Script><![CDATA[
        // ActionScript
    ]]></sw:Script>
</sw:Application>
```

For initialiser code, handle the `creationComplete` event in the `s:Page` tag:

```mxml
<?xml version="1.0"?>
<sw:Application xmlns:sw="http://ns.skywhack.net/2024" creationComplete="initialise()">
    <sw:Script><![CDATA[
        private function initialise():void
        {
            trace("Hello world");
        }
    ]]></sw:Script>
</sw:Application>
```