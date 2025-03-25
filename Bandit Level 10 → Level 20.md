### **Level 10 → Level 11**
#### **Task:** 🔁
Find the password in `data.txt`, which is encoded with ROT13.

#### **Solution:** 🔄
```sh
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

---

### **Level 11 → Level 12**
#### **Task:** 📦
Find the password in `data.txt`, which is a compressed file.

#### **Solution:** 🗂️
```sh
mkdir /tmp/bandit
cp data.txt /tmp/bandit/
cd /tmp/bandit
xxd -r data.txt > output.gz
gzip -d output.gz
tar -xvf output
tar -xvf output2
tar -xvf output3
tar -xvf output4
cat final_file
```

---

### **Level 12 → Level 13**
#### **Task:** 🔍
Find the password inside a hexdump file.

#### **Solution:** 💻
```sh
xxd -r data.txt > output
cat output
```

---

### **Level 13 → Level 14**
#### **Task:** 📡
Send the password via `nc` to retrieve the next password.

#### **Solution:** 📡
```sh
nc localhost 30000
Enter password
```

---

### **Level 14 → Level 15**
#### **Task:** 🔐
Same as before, but use SSL.

#### **Solution:** 🔒
```sh
openssl s_client -connect localhost:30001
Enter password
```

---

### **Level 15 → Level 16**
#### **Task:** 🗝️
Find the private SSH key and log in to Level 16.

#### **Solution:** 🎟️
```sh
cat sshkey.private > ~/.ssh/bandit16
chmod 600 ~/.ssh/bandit16
ssh -i ~/.ssh/bandit16 bandit16@localhost -p 2220
```

---

### **Level 16 → Level 17**
#### **Task:** 📡
Find the reachable port and retrieve the password.

#### **Solution:** 🌐
```sh
nmap -p- localhost
nc localhost PORT_NUMBER
```

---

### **Level 17 → Level 18**
#### **Task:** 🕵️
Find a file owned by `bandit18` and execute it.

#### **Solution:** 🏆
```sh
ls -l /home/bandit17/
./passwordfile
```

---

### **Level 18 → Level 19**
#### **Task:** 🏴‍☠️
Switch user without knowing the password.

#### **Solution:** 🎭
```sh
./bandit18/bin/setuid
```

---

### **Level 19 → Level 20**
#### **Task:** 🎬
Find the password in a script that prints the password when executed.
