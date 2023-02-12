# font-images-dataset
基于五款商用免费字体制作的汉字数据集，附生成工具

### 使用字体

得意黑
三极泼墨体
站酷庆科黄油体
思源黑体
优设标题圆

### 生成工具

```
import os
import pygame

chinese_dir = 'your-font'
if not os.path.exists(chinese_dir):
    os.mkdir(chinese_dir)

pygame.init()
start,end = (0x4E00, 0x9FA5) # 汉字编码范围
for codepoint in range(int(start), int(end)):
    word = chr(codepoint)
    font = pygame.font.Font("your-font.ttf", 250)
    rtext = font.render(word, True, (0, 0, 0), (255, 255, 255))
    rtext = pygame.transform.scale(rtext, (256, 256))
    pygame.image.save(rtext, os.path.join(chinese_dir, word + ".png"))
```
