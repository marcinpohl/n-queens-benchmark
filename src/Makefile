

../bin/queens_cpp_stack: queens.cpp
	clang++ -Ofast -std=c++17 -pthread queens.cpp -o ../bin/queens_cpp_stack

../bin/queens_cpp_heap: queens.cpp
	clang++ -Ofast -std=c++17 -pthread -DALLOC_ON_HEAP queens.cpp -o ../bin/queens_cpp_heap

c++: ../bin/queens_cpp_stack ../bin/queens_cpp_heap
	../bin/queens_cpp_stack --num_from 8 --num_to 16 -w 12 --output ../data/cplus_para_stack.csv
	../bin/queens_cpp_stack --num_from 8 --num_to 16 -w 1 --output ../data/cplus_seq_stack.csv
	../bin/queens_cpp_heap --num_from 8 --num_to 16 -w 12 --output ../data/cplus_para_heap.csv
	../bin/queens_cpp_heap --num_from 8 --num_to 16 -w 1 --output ../data/cplus_seq_heap.csv


../bin/queens_cppat_vbyte: queens_arraytypes.cpp
	clang++ -Ofast -std=c++17 -pthread -DARRAY_VEC_BYTE queens_arraytypes.cpp -o ../bin/queens_cppat_vbyte

../data/cplus_at_vbyte.csv: ../bin/queens_cppat_vbyte
	../bin/queens_cppat_vbyte --num_from 8 --num_to 16 -w 1 --output ../data/cplus_at_vbyte.csv

../bin/queens_cppat_vbool: queens_arraytypes.cpp
	clang++ -Ofast -std=c++17 -pthread -DARRAY_VEC_BOOL queens_arraytypes.cpp -o ../bin/queens_cppat_vbool

../data/cplus_at_vbool.csv: ../bin/queens_cppat_vbool
	../bin/queens_cppat_vbool --num_from 8 --num_to 16 -w 1 --output ../data/cplus_at_vbool.csv

../bin/queens_cppat_new: queens_arraytypes.cpp
	clang++ -Ofast -std=c++17 -pthread -DARRAY_NEW queens_arraytypes.cpp -o ../bin/queens_cppat_new

../data/cplus_at_new.csv: ../bin/queens_cppat_new
	../bin/queens_cppat_new --num_from 8 --num_to 16 -w 1 --output ../data/cplus_at_new.csv

../bin/queens_cppat_stack: queens_arraytypes.cpp
	clang++ -Ofast -std=c++17 -pthread queens_arraytypes.cpp -o ../bin/queens_cppat_stack

../data/cplus_at_stack.csv: ../bin/queens_cppat_stack
	../bin/queens_cppat_stack --num_from 8 --num_to 16 -w 1 --output ../data/cplus_at_stack.csv

c++_array_types: ../data/cplus_at_stack.csv ../data/cplus_at_new.csv ../data/cplus_at_vbool.csv ../data/cplus_at_vbyte.csv


python_seq:
	python queens.py --num_from 8 --num_to 12 --variant python --output ../data/python_pure.csv
	python queens.py --num_from 8 --num_to 16 --variant numba_seq --output ../data/python_numba_seq.csv

python_para:
	python queens.py --num_from 8 --num_to 18 --variant pool --output ../data/python_numba_pool.csv
	python queens.py --num_from 8 --num_to 18 --variant numba_para --output ../data/python_numba_para.csv

python: python_seq python_para


julia_seq:
	julia queens.jl 8 16 seq ../data/julia_seq.csv

julia_para:
	JULIA_NUM_THREADS=32 julia queens.jl 8 18 thread ../data/julia_para.csv

# PATH="$PATH:/cvlabdata2/home/lis/programs/julia/bin" make julia
julia: julia_seq julia_para

plots:
	python plots.py
