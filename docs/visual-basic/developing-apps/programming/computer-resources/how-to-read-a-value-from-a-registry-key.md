---
title: 'Procedura: leggere un valore da una chiave del Registro di sistema in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f88401f6daa7a2108522496c845521474c22cc30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="aa3f6-102">Procedura: leggere un valore da una chiave del Registro di sistema in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa3f6-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="aa3f6-103">Il metodo `GetValue` dell'oggetto `My.Computer.Registry` può essere usato per leggere i valori nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="aa3f6-104">Se la chiave, "Software\MyApp" nell'esempio seguente, non esiste, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="aa3f6-105">Se `ValueName`,  "Name" nell'esempio seguente, non esiste, viene restituito `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="aa3f6-106">Il metodo `GetValue` può essere usato anche per determinare se esiste un determinato valore in una chiave del Registro di sistema specifica.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="aa3f6-107">Quando il codice legge il Registro di sistema da un'applicazione Web, l'utente corrente viene determinato tramite l'autenticazione e la rappresentazione implementata nell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="aa3f6-108">Per leggere un valore da una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="aa3f6-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="aa3f6-109">Usare il metodo `GetValue` (specificando il percorso e il nome) per leggere un valore dalla chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="aa3f6-110">L'esempio seguente legge il valore `Name` da `HKEY_CURRENT_USER\Software\MyApp` e lo visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 <span data-ttu-id="aa3f6-111">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="aa3f6-112">Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-112">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="aa3f6-113">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="aa3f6-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="aa3f6-114">Per determinare se esiste un valore in una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="aa3f6-114">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="aa3f6-115">Usare il metodo `GetValue` per recuperare il valore.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-115">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="aa3f6-116">Il codice seguente controlla se il valore esiste e restituisce un messaggio se il valore non esiste.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-116">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="aa3f6-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="aa3f6-117">Robust Programming</span></span>  
 <span data-ttu-id="aa3f6-118">Nel Registro di sistema sono contenute chiavi di primo livello, o radice, usate per memorizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-118">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="aa3f6-119">Ad esempio, la chiave radice HKEY_LOCAL_MACHINE è usata per memorizzare le impostazioni a livello di computer usate da tutti gli utenti, mentre la chiave HKEY_CURRENT_USER viene usata per memorizzare i dati specifici di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-119">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="aa3f6-120">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="aa3f6-120">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="aa3f6-121">Il nome della chiave è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="aa3f6-121">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="aa3f6-122">L'utente non ha le autorizzazioni per la lettura delle chiavi del Registro di sistema (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="aa3f6-122">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="aa3f6-123">Il nome della chiave supera il limite di 255 caratteri (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="aa3f6-123">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="aa3f6-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa3f6-124">.NET Framework Security</span></span>  
 <span data-ttu-id="aa3f6-125">Per eseguire questo processo, l'assembly richiede un livello di privilegio concesso dalla classe <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-125">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="aa3f6-126">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-126">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="aa3f6-127">Allo stesso modo, l'utente deve disporre degli ACL corretti per la creazione o la scrittura nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-127">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="aa3f6-128">Ad esempio, un'applicazione locale che ha l'autorizzazione di sicurezza dall'accesso di codice potrebbe non avere l'autorizzazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="aa3f6-128">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="aa3f6-129">Per altre informazioni, vedere [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="aa3f6-129">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3f6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa3f6-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <xref:Microsoft.Win32.RegistryHive>  
 [<span data-ttu-id="aa3f6-131">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="aa3f6-131">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
