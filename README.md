# PD2-2
Vladislavs Jagors DT1-2
1 uzdevums 
partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]

for item in partitions:
    label = item.split(";")[0]
    print(label)

    2 uzdevums
    partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]

total_size = 0


for item in partitions:
    
    size = int(item.split(";")[2])
    total_size += size

print(f"Kopā MB: {total_size}")
3 uzdevums

partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]


for item in partitions:
    data = item.split(";")
    label = data[0]
    used_percent = int(data[3]) 

    
    if used_percent >= 90:
        print(f"UZMANĪBU: {label} disks ir pilns!")
4uzdevums
partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]


for item in partitions:
    data = item.split(";")
    label = data[0]
    size_mb = int(data[2])
    
    
    size_gb = size_mb / 1024
    
    
    print(f"{label}: {size_gb:.2f} GB")
    5 uzdevums
    
partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]


search_mount = input("Ievadiet montējuma punktu: ")

found_label = None


for item in partitions:
    data = item.split(";")
    label = data[0]
    mount_point = data[1]
    
    if mount_point == search_mount:
        found_label = label
        break  

if found_label:
    print(found_label)
else:
    print("Nav atrasts")
6 uzdevums

partitions = [
    "System;/;50000;85",
    "Data;/home;150000;40",
    "Cache;/tmp;5000;10",
    "Backup;/mnt/backup;500000;92",
    "USB-Drive;/media/usb;16000;0",
    "Logs;/var/log;10000;95",
    "Database;/var/lib/mysql;80000;70",
    "Shared;/mnt/shared;200000;15",
    "Win-System;/mnt/win;100000;90",
    "Recovery;/recovery;2000;98"
]

def calculate_used_space(data_list):
    result_list = []
    
    for item in data_list:
        parts = item.split(";")
        label = parts[0]
        total_size = int(parts[2])
        used_percent = int(parts[3])
        
        
        used_mb = int(total_size * (used_percent / 100))
        
        
        result_list.append({
            "Label": label,
            "UsedMB": used_mb
        })
        
    return result_list


calculated_data = calculate_used_space(partitions)


for entry in calculated_data:
    print(entry)
