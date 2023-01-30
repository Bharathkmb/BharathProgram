# BharathProgram

#This is the code of the assesment

def job_scheduling(n, jobs):
    jobs.sort(key=lambda x: x[2], reverse=True)
    result = [0, 0]
    end_time = 0
    for i in range(n):
        if jobs[i][0] >= end_time:
            result[0] += 1
            result[1] += jobs[i][2]
            end_time = jobs[i][1]
    return result

n = int(input("Enter the number of Jobs: "))
jobs = []
for i in range(n):
    start_time = int(input("Enter job start time: "))
    end_time = int(input("Enter job end time: "))
    profit = int(input("Enter job profit: "))
    jobs.append([start_time, end_time, profit])

result = job_scheduling(n, jobs)
print("The number of tasks and earnings available for others")
print("Tasks:", n - result[0])
print("Earnings:", result[1])
