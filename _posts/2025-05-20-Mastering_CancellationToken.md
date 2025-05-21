
---
layout: post
title: "Mastering CancellationToken in C#"
date: 2025-05-20 10:00:00 +0600
featured: true
---
# 🚦 Mastering CancellationToken in C#

## 🧠 Why It Matters
In modern .NET applications, **asynchronous programming** is essential—but with it comes the risk of runaway tasks, unresponsive UIs, or server overloads.

Enter `CancellationToken`: a smart way to **inject cancellation logic** into your async workflows.

---

## 🎯 Key Concepts

### ▶️ Inject Control  
🔹 External signal stops task execution gracefully

### ▶️ Graceful Shutdown  
🔹 Check `IsCancellationRequested` inside the task

### ▶️ Linked Tokens  
🔹 Combine multiple cancellation sources

### ▶️ Real-World Use  
🔹 Cancel API calls when the user navigates away

---

## 🛠️ Sample Code

```csharp
using System;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        using CancellationTokenSource cts = new CancellationTokenSource();

        Console.WriteLine("Press any key to cancel...");
        Task.Run(() =>
        {
            Console.ReadKey();
            cts.Cancel();
        });

        try
        {
            await FetchDataAsync(cts.Token);
        }
        catch (OperationCanceledException)
        {
            Console.WriteLine("Operation was cancelled.");
        }
    }

    static async Task FetchDataAsync(CancellationToken token)
    {
        using HttpClient client = new HttpClient();

        Console.WriteLine("Fetching data...");
        HttpResponseMessage response = await client.GetAsync(
            "https://jsonplaceholder.typicode.com/posts", token
        );

        response.EnsureSuccessStatusCode();
        string content = await response.Content.ReadAsStringAsync(token);
        Console.WriteLine("Data fetched successfully.");
    }
}
```

---

## ✅ Takeaway

Using `CancellationToken` not only protects your application from wasteful processing, it also keeps user experience snappy and systems resilient.

---

🔵 Follow for .NET tips: [Connect with me on LinkedIn](https://www.linkedin.com/mynetwork/discovery-see-all/?usecase=PEOPLE_FOLLOWS&followMember=yaseerarafat)
