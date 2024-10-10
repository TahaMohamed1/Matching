term = input("Type term to find: ")

file1 = open("1602_1.txt","r")
outFile = open("outputFile.txt","w+")
for line in file1.readlines():
    
    #remove any useless spaces before and after line
    line = line.strip()
    flag = True
    
    # Check if term provided by the user are in the line in first file
    if term in line:
        file2 = open("buildLog_HKAPM_zc_03_01_00_00_inhouse.txt","r")
        for line2 in file2.readlines():
            
            #check if the line is there in second file as well
            if line in line2:
                flag = False
                outFile.write('%s found in both files \n' % line)
                break
        #if the line is not there in second file
        if flag:
            outFile.write('%s not found in one file \n' % line)
