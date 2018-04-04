# SOPMI
Self complemented sentiment words expansion using seed sentiment words and so-pmi , this method is tested to be effective.  
# 运行方式： 
python SOPMI.py  
# 运行步骤
step 1/4:...seg corpus ...      
step 2/4:...collect cowords ...    
step 3/4:...compute sopmi ...  
step 4/4:...save candiwords ...   
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
1、以65M语料, 2700个词作为语料进行训练，得到结果为:




# 备注：
1、本算法效果受训练语料影响，语料越大，效果越好
2、本算法效率受训练语料影响，语料越大，训练越耗时100个种子词，5M的数据，大约耗时62.679秒
3、候选词的选择，可根据PMI值,词长，词性设定规则，进行筛选














