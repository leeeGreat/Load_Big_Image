# Load_Big_Image
tableView加载大量离线图片时，将各个加载任务放到数组中，创建observer，监听kCFRunLoopBeforeSources（kCFRunLoopBeforeWaiting或者kCFRunLoopBeforeTimers）callback方法里面通过info找到vc，从而执行vc的数组中的任务，执行完一个，移除一个


实验过程中，优化过的代码，用户体验确实好了，流畅了，但是内存消耗的比未优化的要多，使用UI压缩过的图片，然后用runloop 这样加载图片相结合，吃一部分内存来换用户体验，优化过的代码，例子中 反复滑动的话，内存最终稳定在 1.55G，未优化的，最终稳定在 510M左右
