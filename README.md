  ### @explicitHints true
 
# tutorial

## Step 1
**test test This guide is created to assist you throughout the live stream. **

**Step 1**
1. Click on the **Advanced** arrow to expand more category
2. Open the ``||scene.Functions||`` drawer, click on **Make a Function...**
3. Rename **doSomething** to **create_map** 
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-2-of-3/master/assets/Screenshot_2.png)



### ~ tutorialhint
```blocks
function create_map () {
}

```

```ghost

let projectile: Sprite = null
projectile.lifespan = 3000
    if (projectile.isHittingTile(CollisionDirection.Bottom)) {
        projectile.vy = -135
    }
projectile.setImage(img`
        . . . . . . . . . . . . . . . . 
        . . f f f f f f f f . . . . . . 
        . f 7 7 7 7 7 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f 4 . . . . 
        . f 7 7 1 f 1 7 7 7 f f . . . . 
        . f 7 7 1 1 1 7 7 7 f 4 . . . . 
        . f 7 7 7 7 7 f 7 7 f 4 4 . . . 
        . . f f f f f f 7 7 7 f f . . . 
        . . . . f 7 7 7 7 7 7 f 4 . . . 
        . . f 7 7 7 7 7 7 f 7 f 4 4 . . 
        . . f 7 7 7 7 7 7 f 7 7 f f . . 
        . . . . f 7 d d 7 7 7 7 f 4 4 . 
        . . . . f 7 d d d 7 7 7 7 f f 4 
        . . . . f 7 d d d 7 7 7 7 7 7 f 
        . . . . f 7 d f f 7 7 f f f f f 
        . . . . f f f . . f f f . . . . 
        `)

scene.placeOnRandomTile(projectile, 9)      
scene.cameraFollowSprite(projectile)

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (projectile.isHittingTile(CollisionDirection.Bottom)) {
        projectile.vy = -140
    }
})  
``` 


```template

let dino: Sprite = null
scene.setBackgroundColor(1) 
scene.setTileMap(img`
    9 9 9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . . . . . . 7 7 . . . . . . . . . 
    . . . . . . . . . . e e e e e . . . . . 7 e e . . . . . . . . . 
    . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
    7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
    e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
    `, TileScale)
scene.setTile(7, img`
    7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
    6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
    d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
    d d d d d d 6 d d d d d d d 6 d 
    d d d d d d d d d d d d d d d d 
    d 1 1 d 1 d d d d d 1 d d d d d 
    d 1 1 d d d d d d d d d d d d d 
    d d d d d d d d d d d d d d d d 
    d d d d d d d d d d d d d d d d 
    d d d d d d b d d d d d d d 1 d 
    d d d d d d d d d d d d d d d d 
    d d b d d d d d d d d b b d d d 
    d d d d d d d d d d d b b d d d 
    d d d d d d d d d d d d d d d d 
    d d d d d d d 1 d d d d d d d d 
    d d d d d d d d d d d d d d 1 d 
    `, true)
scene.setTile(14, img`
    d 1 d d d d d d d 1 d d d d d d 
    d 1 d d d d d d d 1 d d d d d d 
    d 1 d d d d d d d 1 d d d d d d 
    1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
    d d d d d 1 d d d d d d d 1 d d 
    d d d d d 1 d d d d d d d 1 d d 
    d d d d d 1 d d d d d d d 1 d d 
    1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
    d 1 d d d d d d d 1 d d d d d d 
    d 1 d d d d d d d 1 d d d d d d 
    d 1 d d d d d d d 1 d d d d d d 
    1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
    d d d d d 1 d d d d d d d 1 d d 
    d d d d d 1 d d d d d d d 1 d d 
    d d d d d 1 d d d d d d d 1 d d 
    1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
    `, true)
scene.setTile(2, img`
    c c c c c c c c c c c c c c c c 
    8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
    8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
    6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
    6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
    9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
    6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
    `, true)
scene.setTile(10, img`
    . . . . . . . . . . . . . . . . 
    . . . . . c . . . . . . . . . . 
    . . . . . f 2 2 . . . . . . . . 
    . . . . . f 2 2 2 2 2 . . . . . 
    . . . . . f 2 2 2 2 2 2 2 2 . . 
    . . . . . f 2 2 2 2 2 2 2 . . . 
    . . . . . f 2 2 2 2 . . . . . . 
    . . . . . f 2 . . . . . . . . . 
    . . . . . f . . . . . . . . . . 
    . . . . . f . . . . . . . . . . 
    . . . . . f . . . . . . . . . . 
    . . . . . f . . . . . . . . . . 
    . . . . . f . . . . . . . . . . 
    . . . . f f f . . . . . . . . . 
    . . . f c c c f . . . . . . . . 
    . . f c c c c c f . . . . . . . 
    `, true)
scene.setTile(9, img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, false)
dino = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . f f f f f f f f . . 
    . . . . 4 f 7 7 7 7 7 7 7 7 f . 
    . . . . 4 f 7 7 7 1 f 1 7 7 f . 
    . . . . f f 7 7 7 1 f 1 7 7 f . 
    . . . . 4 f 7 7 7 1 1 1 7 7 f . 
    . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
    . . . f f 7 7 7 f f f f f f . . 
    . . . 4 f 7 7 7 7 7 7 f . . . . 
    . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
    . . f f 7 7 f 7 7 7 7 7 7 f . . 
    . 4 4 f 7 7 7 7 d d 7 f . . . . 
    4 f f 7 7 7 7 d d d 7 f . . . . 
    f 7 7 7 7 7 7 d d d 7 f . . . . 
    f f f f f 7 7 f f d 7 f . . . . 
    . . . . f f f . . f f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(dino, 50, 0)   
dino.ay = 290
scene.cameraFollowSprite(dino)
scene.placeOnRandomTile(dino, 9)
scene.onHitTile(SpriteKind.Player, 10, function (sprite) {
    game.over(true)
})
scene.onHitTile(SpriteKind.Player, 2, function (sprite) {
    game.over(false)
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (dino.isHittingTile(CollisionDirection.Bottom)) {
        dino.vy = -140
    }
})

controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
 game.over(false)
})

controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
 game.over(false)
})

```


## Step 2
**Step 2**
1. Repeat the same step, create another function call **create_dino**
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-2-of-3/master/assets/Screenshot_1.png)

### ~ tutorialhint
```blocks
function create_map () {
}

function create_dino () {
}
```


## Step 3
** Step 3**
1. Follow the below image, drag the blocks from ``||Loops:on start||`` block to the respective function blocks.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-2-of-3/master/assets/Screenshot_3.gif)

### ~ tutorialhint
```blocks
function create_map () {
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . 
        . . . . . . . . . . . . 5 . 5 . . . . . . . 5 . . . . . . . . . 
        . . . . . . . . . . . 5 . 5 . . . . . 5 . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
        . . . 5 . . . . . . d d d d d . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(13, img`
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e b b b b b b d e 
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e d b b b b b b e 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
}


function create_dino () {
    dino = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . f f f f f f f f . . 
        . . . . 4 f 7 7 7 7 7 7 7 7 f . 
        . . . . 4 f 7 7 7 1 f 1 7 7 f . 
        . . . . f f 7 7 7 1 f 1 7 7 f . 
        . . . . 4 f 7 7 7 1 1 1 7 7 f . 
        . . . 4 4 f 7 7 f 7 7 7 7 7 f . 
        . . . f f 7 7 7 f f f f f f . . 
        . . . 4 f 7 7 7 7 7 7 f . . . . 
        . . 4 4 f 7 f 7 7 7 7 7 7 f . . 
        . . f f 7 7 f 7 7 7 7 7 7 f . . 
        . 4 4 f 7 7 7 7 d d 7 f . . . . 
        4 f f 7 7 7 7 d d d 7 f . . . . 
        f 7 7 7 7 7 7 d d d 7 f . . . . 
        f f f f f 7 7 f f d 7 f . . . . 
        . . . . f f f . . f f f . . . . 
        `, SpriteKind.Player)
    controller.moveSprite(dino, 50, 0)
    dino.ay = 290
    scene.cameraFollowSprite(dino)
    scene.placeOnRandomTile(dino, 9)
}

```


## Step 4
** Step 4**
1. Click on the **Advanced** arrow to expand more category
2. Open the ``||scene.Functions||`` drawer, drag the ``||scene.create_map||`` into the ``||Loops:on start||`` block.
3. Next, drag the ``||scene.create_dino||`` into the ``||Loops:on start||`` block.

**Testing**: Test out your game, it should work the same as last week.
### ~ tutorialhint
```blocks
create_map()
create_dino()
```


## Step 5
** Step 5**
1. Click on the tilemap that you have created last week. Let's add Yellow tile to it it.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-2-of-3/master/assets/Screenshot_4.gif)

### ~ tutorialhint
```blocks
create_map()
create_dino()
```


## Step 6
** Step 6**
1. Open the ``||scene.Scene||`` drawer, drag the  ``||scene.set tile to with wall||`` block into the ``||scene.create_map||``  block.
2. Click on the first grey color oval, choose **Yellow** color.

### ~ tutorialhint
```blocks

function create_map () {
    scene.setBackgroundColor(1)
    scene.setTileMap(img`
        9 9 9 . . . . . . . . . . . . . . . . . . . . . 5 . . . . . . . 
        . . . . . . . . . . . . 5 . 5 . . . . . . . 5 . . . . . . . . . 
        . . . . . . . . . . . 5 . 5 . . . . . 5 . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . . . 7 7 . . . 5 . . . . . 
        . . . 5 . . . . . . d d d d d . . . . . 7 e e . . . . . . . . . 
        . . . . . . . . . . . . . . . . . . . 7 e e e . . 7 7 7 . . . a 
        7 7 7 7 7 . . 7 7 . . . . . . . 7 7 7 e e e e . . e e e . . 7 7 
        e e e e e 2 2 e e 2 2 2 2 2 2 2 e e e e e e e 2 2 e e e 2 2 e e 
        `, TileScale)
    scene.setTile(7, img`
        7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 7 
        6 6 7 6 7 6 7 6 6 d 6 7 7 6 7 7 
        d d 6 7 7 6 7 d d d 7 6 d 6 7 6 
        d d d d d d 6 d d d d d d d 6 d 
        d d d d d d d d d d d d d d d d 
        d 1 1 d 1 d d d d d 1 d d d d d 
        d 1 1 d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d b d d d d d d d 1 d 
        d d d d d d d d d d d d d d d d 
        d d b d d d d d d d d b b d d d 
        d d d d d d d d d d d b b d d d 
        d d d d d d d d d d d d d d d d 
        d d d d d d d 1 d d d d d d d d 
        d d d d d d d d d d d d d d 1 d 
        `, true)
    scene.setTile(14, img`
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        d 1 d d d d d d d 1 d d d d d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        d d d d d 1 d d d d d d d 1 d d 
        1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 
        `, true)
    scene.setTile(13, img`
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e b b b b b b d e 
        d 1 1 1 1 1 1 b d 1 1 1 1 1 1 b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d b 1 d d d d d d b 
        1 d d d d d d d 1 d d d d d d d 
        b b b b b b d e d b b b b b b e 
        `, true)
    scene.setTile(2, img`
        c c c c c c c c c c c c c c c c 
        8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 8 
        8 8 8 6 6 6 8 8 8 6 6 6 6 8 8 8 
        6 6 8 8 8 6 6 6 6 6 6 8 8 8 8 6 
        6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 6 
        9 9 6 6 6 6 6 9 9 9 9 6 6 6 9 9 
        6 6 6 6 9 9 9 6 6 6 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 
        `, true)
    scene.setTile(9, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
    scene.setTile(10, img`
        . . . . . . . . . . . . . . . . 
        . . . . . c . . . . . . . . . . 
        . . . . . f 2 2 . . . . . . . . 
        . . . . . f 2 2 2 2 2 . . . . . 
        . . . . . f 2 2 2 2 2 2 2 2 . . 
        . . . . . f 2 2 2 2 2 2 2 . . . 
        . . . . . f 2 2 2 2 . . . . . . 
        . . . . . f 2 . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . . f . . . . . . . . . . 
        . . . . f f f . . . . . . . . . 
        . . . f c c c f . . . . . . . . 
        . . f c c c c c f . . . . . . . 
        `, true)
    scene.setTile(5, img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, false)
}
```



## Step 7
** Step 7**
1. Click on the **Advanced** arrow to expand more category
2. Open the ``||scene.Functions||`` drawer, click on **Make a Function...**
3. Rename **doSomething** to **create_eggs** 
4. Open the ``||scene.Functions||`` drawer, drag the ``||scene.create_eggs||`` into the ``||Loops:on start||`` block.
![screenshots](https://raw.githubusercontent.com/TomatoCube18/tutorial-hungry-dino-part-2-of-3/master/assets/Screenshot_6.png)

### ~ tutorialhint
```blocks
create_map()
create_dino()
create_eggs()
function create_eggs () {
}
```


## Step 8
** Step 8**
1. Open the ``||scene.Scene||`` drawer, drag the ``||variables.set tile list to array of all tiles||``  into the ``||scene.create_eggs||`` block
2. Click on the grey color oval, choose **Yellow** color.
3. Open the ``||loops.Loops||`` drawer, drag the ``||loops.for element values of list||`` block into the ``||scene.create_eggs||`` block
4. Click on the **list**, change it to **tile list**

### ~ tutorialhint
```blocks
function create_eggs () {
    tile_list = scene.getTilesByType(5)
    for (let value3 of tile_list) {    	
    }
}
```


## Step 9
** Step 9**
1. Open the ``||sprites.Sprites||`` drawer, drag the  ``||variables.set mySprite||`` inside the ``||loops.for element||`` block
2. Click on the grey color oval, select **Gallery** view. Scroll to find the image of an egg, select it and hit "OK". 
3. Rename the character from **mySprite** to **egg**
4. Change the kind from **Player** to **Food**
5. Open the ``||scene.Scene||`` drawer, drag the ``||scene.on top of myTile place mySprite||``  inside the ``||loops.for element||`` block
6. Change **myTile** to **value**
7. Change **mySprite** to **egg**

### ~ tutorialhint
```blocks
function create_eggs () {
    tile_list = scene.getTilesByType(5)
    for (let value of tile_list) {  
        egg = sprites.create(img`
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . f f . . . . . . . 
            . . . . . . f 5 5 f . . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 1 1 5 f . . . . . 
            . . . . f 5 5 5 1 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . f 5 5 5 5 5 5 f . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . f 5 5 5 5 f . . . . . 
            . . . . . . f f f f . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Food)
        scene.place(value, egg)      	
    }
}
```



> Open this page at [https://tomatocube18.github.io/test_arcade/](https://tomatocube18.github.io/test_arcade/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/tomatocube18/test_arcade** and import

## Edit this project ![Build status badge](https://github.com/tomatocube18/test_arcade/workflows/MakeCode/badge.svg)

To edit this repository in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/tomatocube18/test_arcade** and click import

## Blocks preview

This image shows the blocks code from the last commit in master.
This image may take a few minutes to refresh.

![A rendered view of the blocks](https://github.com/tomatocube18/test_arcade/raw/master/.github/makecode/blocks.png)

#### Metadata (used for search, rendering)

* for PXT/arcade
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
