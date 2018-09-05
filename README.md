# AI_Make_Music

“案例一AI作曲训练结果” 文件夹里包含我训练了 100 多个 Epoch 得到的结果，
可直接用于生成 mp3 音乐。

music_midi 文件夹里是训练所用的 MIDI 文件。

1.mid 是用于 test_music21.py
（测试 Music21 这个 Python 的库）的 MIDI 文件，跟训练和测试没有关系。

=======
训练：

运行 python train.py 即可开始训练。

默认训练 100 个 Epoch，你可以提早结束训练（Ctrl + C）。

=======
生成 mp3 音乐
（先生成 output.mid 这个 MIDI 文件，再从 output.mid 生成 output.mp3 文件）：

训练完很多个 Epoch （训练几个 Epoch 是不够的，音乐比较单调）之后，
记得要将训练时生成的参数文件中 loss（损失）较小的那个改名为 best-weights.hdf5，
保证其位于 generate.py 同级目录下，
运行 python generate.py 即可生成 mp3 音乐。

如果等不了那么久，可以用我提供在“案例一AI作曲训练结果”文件夹里
的参数文件 best-weights.hdf5 和 data/notes 文件。
使 data/notes 文件 和 best-weights.hdf5 参数文件位于 generate.py 同级目录下，
运行 python generate.py 即可生成 mp3 音乐。

=======
注意：
Windows 用户没有貌似 timidity 这个软件，可以使用其他软件来从 MIDI 文件生成 mp3。
macOS 用户直接用 GarageBand 这样的软件打开 MIDI 文件即可播放音乐。
