

```
import pcbnew

board = pcbnew.GetBoard()

def mm(x, y):
    return pcbnew.VECTOR2I(int(x * 1_000_000), int(y * 1_000_000))

start = mm(10, 10)
end = mm(50, 50)

track = pcbnew.PCB_TRACK(board)
track.SetStart(start)
track.SetEnd(end)
track.SetLayer(pcbnew.F_Cu)
track.SetWidth(int(0.25 * 1_000_000))  # 0.25 mm

board.Add(track)
pcbnew.Refresh()


```