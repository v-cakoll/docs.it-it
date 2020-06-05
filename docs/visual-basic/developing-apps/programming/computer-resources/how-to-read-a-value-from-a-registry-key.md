---
title: 'Procedura: Leggere un valore da una chiave del Registro di sistema'
ms.date: 07/20/2015
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
ms.openlocfilehash: 74069b111f4316eb81c74f5e62c1fbff6ab8f4b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401849"
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="2885c-102">Procedura: leggere un valore da una chiave del Registro di sistema in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2885c-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>

<span data-ttu-id="2885c-103">Il metodo `GetValue` dell'oggetto `My.Computer.Registry` può essere usato per leggere i valori nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="2885c-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="2885c-104">Se la chiave, "Software\MyApp" nell'esempio seguente, non esiste, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2885c-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="2885c-105">Se `ValueName`,  "Name" nell'esempio seguente, non esiste, viene restituito `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2885c-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="2885c-106">Il metodo `GetValue` può essere usato anche per determinare se esiste un determinato valore in una chiave del Registro di sistema specifica.</span><span class="sxs-lookup"><span data-stu-id="2885c-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="2885c-107">Quando il codice legge il Registro di sistema da un'applicazione Web, l'utente corrente viene determinato tramite l'autenticazione e la rappresentazione implementata nell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="2885c-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="2885c-108">Per leggere un valore da una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2885c-108">To read a value from a registry key</span></span>  
  
- <span data-ttu-id="2885c-109">Usare il metodo `GetValue` (specificando il percorso e il nome) per leggere un valore dalla chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2885c-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="2885c-110">L'esempio seguente legge il valore `Name` da `HKEY_CURRENT_USER\Software\MyApp` e lo visualizza in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2885c-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#4)]  
  
 <span data-ttu-id="2885c-111">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2885c-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="2885c-112">Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="2885c-112">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="2885c-113">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="2885c-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="2885c-114">Per determinare se esiste un valore in una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2885c-114">To determine whether a value exists in a registry key</span></span>  
  
- <span data-ttu-id="2885c-115">Usare il metodo `GetValue` per recuperare il valore.</span><span class="sxs-lookup"><span data-stu-id="2885c-115">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="2885c-116">Il codice seguente controlla se il valore esiste e restituisce un messaggio se il valore non esiste.</span><span class="sxs-lookup"><span data-stu-id="2885c-116">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2885c-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="2885c-117">Robust Programming</span></span>  

 <span data-ttu-id="2885c-118">Nel Registro di sistema sono contenute chiavi di primo livello, o radice, usate per memorizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="2885c-118">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="2885c-119">Ad esempio, la chiave radice HKEY_LOCAL_MACHINE è usata per memorizzare le impostazioni a livello di computer usate da tutti gli utenti, mentre la chiave HKEY_CURRENT_USER viene usata per memorizzare i dati specifici di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="2885c-119">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="2885c-120">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="2885c-120">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="2885c-121">Il nome della chiave è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2885c-121">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="2885c-122">L'utente non ha le autorizzazioni per la lettura delle chiavi del Registro di sistema (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2885c-122">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="2885c-123">Il nome della chiave supera il limite di 255 caratteri (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2885c-123">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2885c-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2885c-124">.NET Framework Security</span></span>  

 <span data-ttu-id="2885c-125">Per eseguire questo processo, l'assembly richiede un livello di privilegio concesso dalla classe <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="2885c-125">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="2885c-126">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="2885c-126">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="2885c-127">Allo stesso modo, l'utente deve disporre degli ACL corretti per la creazione o la scrittura nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2885c-127">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="2885c-128">Ad esempio, un'applicazione locale che ha l'autorizzazione di sicurezza dall'accesso di codice potrebbe non avere l'autorizzazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2885c-128">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="2885c-129">Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="2885c-129">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2885c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2885c-130">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.Win32.RegistryHive>
- [<span data-ttu-id="2885c-131">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2885c-131">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
