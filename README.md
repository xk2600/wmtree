# wmtree
Docked Pop-out Hierarchical Task (window) switcher (selector)

Allowing a single view of all deskops in the same fashion as
`ps -d` or `pstree`. Allowing easy and dynamic selection of 
the active task one would like to work on.

# Summary of usage

- First launch for an individual user+display creates a server,
  daemonizes, and Listens on a unix socket in the users XDG_RUNTIME_DIR.

- Subsequent calls to the binary send commands to the listening socket.

  > **`NOTE`**--any client which abides by the call structure can send
  > commands to the socket, but until it exits the socket will be locked
  > from receiving commands from other clients (including the native
  > client.)

- On startup, the current focused app, its windows, and it's window's
  children are displayed (for when windows exist within windows).
  
- typing filters the window list to items which match the typed query

- up, down, and the mouse scroll-wheel arrows allow traversal of the 
  current view of the tree
  
- left and right keys expand and collapse the selected portion of the tree

- `Super`-`ESC` Expands the Selector from the left side of screen,
  making visible the tree-view of the window

- As options are selected a scaled live image of the the window is 
  expanded to consume the full view on the right (using compositing).
  


