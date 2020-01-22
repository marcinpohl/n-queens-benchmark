all:
	$(MAKE) c+1
	$(MAKE) c+2
	$(MAKE) gol

c++:
	$(MAKE) clean
	clang++  queens.cpp -Ofast -stdlib=libc++ -pthread -std=gnu++14
	time ./a.out -n0 8  -n1 15 > cplu1.log
	time ./a.out -n0 15 -n1 18 > cplu2.log
	time ./a.out -n0 18 -n1 19 > cplu3.log

c+1:
	$(MAKE) clean
	clang++  queens1.cpp -Ofast -stdlib=libc++ -pthread -std=gnu++14
	time ./a.out -n0 8  -n1 15 > cplu1.log
	time ./a.out -n0 15 -n1 18 > cplu2.log
	time ./a.out -n0 18 -n1 19 > cplu3.log

c+2:
	$(MAKE) clean
	clang++  queens2.cpp -Ofast -stdlib=libc++ -pthread -std=gnu++14
	time ./a.out -n0 8  -n1 15 > cplu1.log
	time ./a.out -n0 15 -n1 18 > cplu2.log
	time ./a.out -n0 18 -n1 19 > cplu3.log

c+3:
	$(MAKE) clean
	clang++  queens2.cpp -Ofast -stdlib=libc++ -pthread -std=gnu++14
	time ./a.out -n0 8  -n1 15 > cplu1.log
	time ./a.out -n0 15 -n1 18 > cplu2.log
	time ./a.out -n0 18 -n1 19 > cplu3.log

gol:
	rm -f queens
	go build queens.go
	time ./queens -n0 8  -n1 14 > gola1.log
	time ./queens -n0 15 -n1 17 > gola2.log
	time ./queens -n0 18 -n1 18 > gola3.log

pyt:
	python queens.py > queens.log

foo:
	$(MAKE) clean
	clang++  queens.cpp -Ofast -stdlib=libc++ -pthread -std=gnu++14
	time ./a.out -n0 17 -n1 19 > cplu4.log
	go build queens.go
	time ./queens -n0 18 -n1 18 > gola4.log

clean:
	rm -f *.o a.out queens
