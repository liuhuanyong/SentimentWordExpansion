# SOPMI
Self complemented sentiment words expansion(情感词扩展) using seed sentiment words and so-pmi , this method is tested to be effective.  
# 运行方式： 
python SOPMI.py  
# 运行步骤
step 1/4:   seg corpus       
step 2/4:   collect cowords     
step 3/4:   compute sopmi   
step 4/4:   save candiwords    
# 训练
1）输入：  
1、5W个文档，每个文档为一行，保存在'./data/train.txt'中  
2、种子情感词：正负情感词各50个，共100个，格式为 ‘词\t极性’，保存在'./data/sentiment_words.txt'中  
2）输出：  
1、格式：复杂,29.47870186147108,neg,2,a (词语,pmi值,情感极性,词长,词性)  
2、正向扩充情感候选词，保存在'./data/candi_pos.txt'中   
3、负向扩充情感候选词，保存在'./data/candi_neg.txt'中  
3）参数：  
1、window_size: 默认为5， 左右窗口为5， 作为词共现窗口  
# 结果：
以本项目5M语料，100个情感种子词作为语料进行训练得到的结果，可参考2）输出  
以65M语料, 2700个情感种子词作为语料进行训练，按照sopmi进行从大到小排序，分别取Pos Top20, Neg Top20:  
1、Pos Top20  中
word	sopmi	polarity	word_length	postag  
引领	580.764033	pos	2	v  
带动	427.556128	pos	2	v  
特色	412.6122548	pos	2	n  
打造	405.0244191	pos	2	v   
创造	380.5108446	pos	2	v  
社会主义	331.5382073	pos	4	n  
中华民族	321.9725365	pos	4	nz  
伟大	316.8030181	pos	2	a  
动能	315.5511916	pos	2	n  
活力	311.7528844	pos	2	n  
创新	309.235422	pos	2	v  
赢得	306.6883568	pos	2	v  
领先	305.4931831	pos	2	n  
现代	302.7672176	pos	2	t  
取得	298.8067767	pos	2	v    
美好生活	293.230993	pos	4	i  
复兴	291.6213326	pos	2	a  
成绩	290.1984593	pos	2	n  
影响力	288.9637384	pos	3	n  
强劲	286.3402434	pos	2	a  
2、Neg Top20  
word	sopmi	polarity	word_length	postag  
造成	-2312.1367	neg	2	v  
导致	-2138.488406	neg	2	v  
问题	-2134.288251	neg	2	n  
没有	-2116.627452	neg	2	v  
可能	-2107.47546	neg	2	v  
影响	-2081.211927	neg	2	vn  
环境	-2043.664368	neg	2	n  
出现	-2033.126848	neg	2	v  
严重	-1908.866578	neg	2	a  
已经	-1736.882867	neg	2	d  
甚至	-1723.443634	neg	2	d  
不能	-1687.246421	neg	2	v  
情况	-1671.459319	neg	2	n  
进行	-1641.724153	neg	2	v  
存在	-1588.600102	neg	2	v  
现象	-1523.298223	neg	2	n  
就是	-1500.296208	neg	2	d  
发生	-1436.646156	neg	2	v  
时候	-1395.88544	neg	2	n  
原因	-1375.6175	neg	2	n  
# 备注：
1、本算法效果受训练语料影响，语料越大，效果越好  
2、本算法效率受训练语料影响，语料越大，训练越耗时100个种子词，5M的数据，大约耗时62.679秒  
3、候选词的选择，可根据PMI值，词长，词性设定规则，进行筛选  
