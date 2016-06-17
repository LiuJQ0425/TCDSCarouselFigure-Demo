# TCDSCarouselFigure-Demo
无限轮播图

可以看作一个自定义的控件。实现方法有两种，下面分别介绍。



//  1  使用UIImage数组初始化  部分代码

    _carouselFigure = [[TCDSCarouselFigure alloc]initWithImages:self.images
                                                          frame:CGRectMake(0, 22, self.view.frame.size.width, self.view.frame.size.width * 9 / 16)];
    [self.view addSubview:_carouselFigure];
    _carouselFigure.timeInterval = 2;
    _carouselFigure.delegate = self;
    [_carouselFigure startLoop];

//懒加载UIImage数组

-(NSMutableArray *)images {
    if (!_images) {
        _images = [NSMutableArray arrayWithArray:@[[UIImage imageNamed:@"1"],[UIImage imageNamed:@"2"],[UIImage imageNamed:@"3"],[UIImage imageNamed:@"4"],[UIImage imageNamed:@"5"],[UIImage imageNamed:@"6"],[UIImage imageNamed:@"7"],[UIImage imageNamed:@"8.jpg"],[UIImage imageNamed:@"9.jpg"]]];
    }
    return _images;
}


//  2  使用图片下载链接初始化  部分代码

    _arr = [NSMutableArray arrayWithObjects:@"http://bt.img.17gwx.com/topic/0/4/dllf/600x330", @"http://bt.img.17gwx.com/topic/0/5/d1he/600x330", @"http://bt.img.17gwx.com/topic/0/12/c1NdYQ/600x330", @"http://bt.img.17gwx.com/topic/0/6/dFVY/600x330", @"http://bt.img.17gwx.com/topic/0/2/cFdZ/600x330", @"http://bt.img.17gwx.com/topic/0/21/cFBYZQ/600x330", nil];
    
    TCDSCarouselFigure *carouselFigure = [[TCDSCarouselFigure alloc]initWithImageURLs:_arr
                                                                                frame:CGRectMake(0, 22, self.view.frame.size.width, self.view.frame.size.width * 9 / 16)];
    carouselFigure.pageControl.pageIndicatorTintColor = [UIColor purpleColor];
    carouselFigure.pageControl.currentPageIndicatorTintColor = [UIColor cyanColor];
    
    [self.view addSubview:carouselFigure];







本人第一个demo，希望高人指点。



