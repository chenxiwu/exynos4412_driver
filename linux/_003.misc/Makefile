obj-m += misc_module.o

KERNEL = /home/wangbing/workspace/exynos4412/source/linux-3.5
ROOTFS = /home/wangbing/workspace/exynos4412/rootfs

all:
	@make -C $(KERNEL) M=`pwd` modules > modules.log
	@arm-linux-gcc misc_app.c -o app > app.log
	@rm -rf $(ROOTFS)/test/*
	@cp -f *.ko $(ROOTFS)/test
	@cp -f app $(ROOTFS)/test
	@echo "\033[31m >>>>>> make all successful <<<<<< \033[0m"
	@make clean
clean:
	@make -C $(KERNEL) M=`pwd` modules clean > clean.log
	@rm -f app *.log
	@echo "\033[31m >>>>>> make clean successful <<<<<< \033[0m"
