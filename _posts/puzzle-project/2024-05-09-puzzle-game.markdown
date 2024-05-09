---
layout: post
title:  "The Puzzle Project"
date:   2024-05-09 12:30:00 +0200
categories: puzzle project
---
Lots of different code examples blabal

```lua
function generateRandomBlueprint(width,height,filled_cells_target,size_variance)
    local variance = size_variance or 0
    local width = flr(width + rnd(variance+1))
    local height = flr(height + rnd(variance+1))
    local filled_cells_target = filled_cells_target or flr((width*height)/2)

    --create empty userdata
    local table = userdata(i8,width,height)
    for y = 0, height-1 do 
        for x = 0, width-1 do
            table[x+y*width] = 0
        end
    end

    --go over randomly and add cells until meet target. RISKY!
	local filled_cells = 0
	while filled_cells < filled_cells_target do
		local x = flr(rnd(width))
		local y = flr(rnd(height))
		if table[x+y*width] == 0 then
			table[x+y*width] = 1
			filled_cells += 1
		end
	end
	
	--generate the blueprint groups
	local bp = { x = {}, y = {} }
	for y = 1, height do
		bp.y[y] = generateGroups(table,width,nil,y)
	end
	for x = 1, width do
		bp.x[x] = generateGroups(table,height,x,nil)
    end
    return bp 
end
```

## Heading

Sme other text

## Heading 2
