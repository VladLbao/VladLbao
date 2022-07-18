function love.load()
target = {}
target.x = 650
target.y = 300
target.radius = 50

score = 0
timer = 0

gameFont = love.graphics.newFont(35)



end

function love.update(dt)

end

function love.draw()
love.graphics.setColor(6/255, 98/255, 196/255)
love.graphics.circle("fill", target.x, target.y, target.radius)


love.graphics.setColor(0, 255/255, 149/255)
love.graphics.setFont(gameFont)
love.graphics.print(score, 0, 0)
end

function love.mousepressed( x, y, button, istouch, presses )
  if button == 1 then
   local mouseTotarget = distanceBetwen(x, y, target.x, target.y)
   if mouseTotarget < target.radius then
    score = score + 1
    target.x = math.random(target.radius, love.graphics.getWidth() - target.radius)
    target.y = math.random(target.radius, love.graphics.getHeight() - target.radius)


   end
  end
end

function distanceBetwen(x1, y1, x2, y2)
  return math.sqrt( (x2 - x1)^2 + (y2 - y1)^2 )
end   
