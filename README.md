# athens-witeboard
Integration of Athens with Witeboard.com for drawing support with the help of Alfred or Expanso

## Requirements
* Mac with alfred powerpack installed for the alfred snippet
* Any device that support [Expanso](https://github.com/federico-terzi/espanso)

## Demo
[Loom Recording](https://www.loom.com/share/839e0ea8b356478f93aae8bee4a6db9d)
## Integrating Witeboard.com via Alfred 
1. Create a snippet in Alfred
2. In the snippet that you open up, copy the following
```
{{iframe: https://witeboard.com/{random:UUID}}}
{cursor}
```
3. Alternatively, download the .alfredsnippets [file](https://github.com/sawhney17/athens-witeboard/raw/main/Athens%20Witeboard.alfredsnippets) in this repo. 
## Integrating Witeboard.com via Expanso
Credits to [Phrohdoh](https://github.com/phrohdoh) for this implementation + insutructions
1. Once espanso is installed, see https://espanso.org/docs/get-started/#configuration (which'll have you execute espanso path) 
2. Then go to  https://espanso.org/docs/configuration/#structure and create a user config file (I recommend not adding custom stuff to default.yml 
3. Remove the default matches with the following contents (modified as you want, of course).

```
name: athens-research
parent: default

matches:
  - trigger: "/draw"
    replace: "{{iframe: https://witeboard.com/{{board_id}}}}"
    vars:
      - name: board_id
        type: shell
        params:
          cmd: "[guid]::NewGuid().ToString()"
```

## Where to go from here
Integrating [Excalidraw](https://github.com/excalidraw/excalidraw), widely regarded as the best free virtual whiteboard with Athens through this (repo)[https://github.com/sawhney17/athens-excalidraw].
