---
title: 'Procedura: creare una chiave nel Registro di sistema (Visual C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96d34df3314494fc96ad8b55d7462b67dcc7bd72
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="747f8-102">Procedura: creare una chiave nel Registro di sistema (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="747f8-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="747f8-103">Nell'esempio riportato di seguito viene aggiunta la coppia di valori "Name" e "Isabella" alla chiave "Names"del Registro di sistema dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="747f8-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="747f8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="747f8-104">Example</span></span>  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="747f8-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="747f8-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="747f8-106">Copiare il codice e incollarlo nel metodo `Main` di un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="747f8-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="747f8-107">Sostituire il parametro `Names` con il nome di una chiave esistente direttamente nel nodo HKEY_CURRENT_USER del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="747f8-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="747f8-108">Sostituire il parametro `Name` con il nome di un valore esistente direttamente nel nodo Names.</span><span class="sxs-lookup"><span data-stu-id="747f8-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="747f8-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="747f8-109">Robust Programming</span></span>  
 <span data-ttu-id="747f8-110">Esaminare la struttura del Registro di sistema per individuare un percorso adatto per la chiave.</span><span class="sxs-lookup"><span data-stu-id="747f8-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="747f8-111">Può essere necessario, ad esempio, aprire la chiave Software dell'utente corrente e creare una chiave con il nome della propria società,</span><span class="sxs-lookup"><span data-stu-id="747f8-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="747f8-112">quindi aggiungere i valori del Registro di sistema alla chiave della società stessa.</span><span class="sxs-lookup"><span data-stu-id="747f8-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="747f8-113">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="747f8-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="747f8-114">Il nome della chiave è null.</span><span class="sxs-lookup"><span data-stu-id="747f8-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="747f8-115">L'utente non dispone di autorizzazioni per la creazione di chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="747f8-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="747f8-116">Il nome della chiave supera il limite di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="747f8-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="747f8-117">La chiave è chiusa.</span><span class="sxs-lookup"><span data-stu-id="747f8-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="747f8-118">La chiave del Registro di sistema è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="747f8-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="747f8-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="747f8-119">.NET Framework Security</span></span>  
 <span data-ttu-id="747f8-120">È più sicuro scrivere i dati nella cartella dell'utente, ovvero `Microsoft.Win32.Registry.CurrentUser`, anziché nel computer locale, ovvero `Microsoft.Win32.Registry.LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="747f8-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="747f8-121">Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già.</span><span class="sxs-lookup"><span data-stu-id="747f8-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="747f8-122">È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="747f8-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="747f8-123">I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi.</span><span class="sxs-lookup"><span data-stu-id="747f8-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="747f8-124">Per evitare che ciò accada, usare il metodo `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="747f8-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="747f8-125">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="747f8-125">method.</span></span> <span data-ttu-id="747f8-126">Restituisce null se la chiave non esiste.</span><span class="sxs-lookup"><span data-stu-id="747f8-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="747f8-127">Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="747f8-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747f8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="747f8-128">See Also</span></span>  
 <span data-ttu-id="747f8-129"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="747f8-129"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="747f8-130">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="747f8-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="747f8-131">[File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="747f8-131">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 <span data-ttu-id="747f8-132">[Read, write and delete from the registry with C#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C) (Leggere, scrivere ed eliminare dal Registro di sistema con C#)</span><span class="sxs-lookup"><span data-stu-id="747f8-132">[Read, write and delete from the registry with C#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)</span></span>

