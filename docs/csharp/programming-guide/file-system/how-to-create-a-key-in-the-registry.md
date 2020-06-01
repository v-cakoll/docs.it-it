---
title: Come creare una chiave nel registro di sistema-guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 9e340083ffca118337dc9a53bdf20808cd1b15cb
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241630"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="7d1a5-102">Come creare una chiave nel registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7d1a5-102">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="7d1a5-103">Nell'esempio riportato di seguito viene aggiunta la coppia di valori "Name" e "Isabella" alla chiave "Names"del Registro di sistema dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d1a5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d1a5-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d1a5-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7d1a5-105">Compiling the Code</span></span>  
  
- <span data-ttu-id="7d1a5-106">Copiare il codice e incollarlo nel metodo `Main` di un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="7d1a5-107">Sostituire il parametro `Names` con il nome di una chiave esistente direttamente nel nodo HKEY_CURRENT_USER del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="7d1a5-108">Sostituire il parametro `Name` con il nome di un valore esistente direttamente nel nodo Names.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7d1a5-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7d1a5-109">Robust Programming</span></span>  
 <span data-ttu-id="7d1a5-110">Esaminare la struttura del Registro di sistema per individuare un percorso adatto per la chiave.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="7d1a5-111">Può essere necessario, ad esempio, aprire la chiave Software dell'utente corrente e creare una chiave con il nome della propria società,</span><span class="sxs-lookup"><span data-stu-id="7d1a5-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="7d1a5-112">quindi aggiungere i valori del Registro di sistema alla chiave della società stessa.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="7d1a5-113">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="7d1a5-113">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="7d1a5-114">Il nome della chiave è null.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-114">The name of the key is null.</span></span>  
  
- <span data-ttu-id="7d1a5-115">L'utente non dispone di autorizzazioni per la creazione di chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-115">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="7d1a5-116">Il nome della chiave supera il limite di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-116">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="7d1a5-117">La chiave è chiusa.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-117">The key is closed.</span></span>  
  
- <span data-ttu-id="7d1a5-118">La chiave del Registro di sistema è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-118">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="7d1a5-119">Sicurezza .NET</span><span class="sxs-lookup"><span data-stu-id="7d1a5-119">.NET Security</span></span>  
 <span data-ttu-id="7d1a5-120">È più sicuro scrivere i dati nella cartella dell'utente, ovvero `Microsoft.Win32.Registry.CurrentUser`, anziché nel computer locale, ovvero `Microsoft.Win32.Registry.LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="7d1a5-121">Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="7d1a5-122">È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="7d1a5-123">I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="7d1a5-124">Per evitare che ciò accada, usare il metodo `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="7d1a5-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="7d1a5-125">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-125">method.</span></span> <span data-ttu-id="7d1a5-126">Restituisce null se la chiave non esiste.</span><span class="sxs-lookup"><span data-stu-id="7d1a5-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="7d1a5-127">Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="7d1a5-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1a5-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d1a5-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="7d1a5-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7d1a5-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d1a5-130">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7d1a5-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- <span data-ttu-id="7d1a5-131">[Read, write and delete from the registry with C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C) (Leggere, scrivere ed eliminare dal Registro di sistema con C#)</span><span class="sxs-lookup"><span data-stu-id="7d1a5-131">[Read, write and delete from the registry with C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)</span></span>
