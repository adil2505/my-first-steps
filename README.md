# Use the file name mbox-short.txt as the file name
fname = input("Enter file name: ")
fh = open(fname)
count = 0
total = 0
for line in fh:
    if not line.startswith("X-DSPAM-Confidence:"):
        continue
    #print(line)
    if line.startswith("X-DSPAM-Confidence:"):
        x = line.find("0")
        numbers = float(line[x:])
        count = count + 1
        total = total + numbers
Average = total/count
print("Average spam confidence:", Average)
