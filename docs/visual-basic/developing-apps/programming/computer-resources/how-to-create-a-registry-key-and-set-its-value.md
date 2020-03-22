---
title: 'Procedura: creare una chiave del Registro di sistema e impostarne il valore'
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 459c4b3f971009ee4b6b669c55bc058db0826595
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349196"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="4119a-102">Procedura: creare una chiave del Registro di sistema e impostarne il valore in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4119a-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>

<span data-ttu-id="4119a-103">Il metodo `CreateSubKey` dell'oggetto `My.Computer.Registry` consente di creare una chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4119a-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>

## <a name="procedure"></a><span data-ttu-id="4119a-104">Procedura</span><span class="sxs-lookup"><span data-stu-id="4119a-104">Procedure</span></span>

### <a name="to-create-a-registry-key"></a><span data-ttu-id="4119a-105">Per creare una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4119a-105">To create a registry key</span></span>

- <span data-ttu-id="4119a-106">Usare il metodo `CreateSubKey` specificando l'hive in cui inserire la chiave, nonché il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="4119a-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="4119a-107">Per il parametro `Subkey` non esiste distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4119a-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="4119a-108">Nell'esempio che segue viene creata la chiave del Registro di sistema `MyTestKey` in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="4119a-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="4119a-109">Per creare una chiave del Registro di sistema e impostarne il valore</span><span class="sxs-lookup"><span data-stu-id="4119a-109">To create a registry key and set a value in it</span></span>

1. <span data-ttu-id="4119a-110">Usare il metodo `CreateSubkey` specificando l'hive in cui inserire la chiave, nonché il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="4119a-110">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="4119a-111">Nell'esempio che segue viene creata la chiave del Registro di sistema `MyTestKey` in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="4119a-111">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. <span data-ttu-id="4119a-112">Impostare il valore con il metodo `SetValue`.</span><span class="sxs-lookup"><span data-stu-id="4119a-112">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="4119a-113">In questo esempio viene impostato il valore stringa.</span><span class="sxs-lookup"><span data-stu-id="4119a-113">This example sets the string value.</span></span> <span data-ttu-id="4119a-114">"MyTestKeyValue" su "This is a test value".</span><span class="sxs-lookup"><span data-stu-id="4119a-114">"MyTestKeyValue" to "This is a test value".</span></span>

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a><span data-ttu-id="4119a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4119a-115">Example</span></span>

<span data-ttu-id="4119a-116">Nell'esempio che segue viene creata la chiave del Registro di sistema `MyTestKey` in HKEY_CURRENT_USER e il valore stringa `MyTestKeyValue` viene impostato su `This is a test value`.</span><span class="sxs-lookup"><span data-stu-id="4119a-116">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a><span data-ttu-id="4119a-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4119a-117">Robust Programming</span></span>

<span data-ttu-id="4119a-118">Esaminare la struttura del Registro di sistema per individuare un percorso adatto per la chiave.</span><span class="sxs-lookup"><span data-stu-id="4119a-118">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="4119a-119">Può essere ad esempio necessario aprire la chiave HKEY_CURRENT_USER\Software dell'utente corrente e creare una chiave con il nome della società,</span><span class="sxs-lookup"><span data-stu-id="4119a-119">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="4119a-120">quindi aggiungere i valori del Registro di sistema alla chiave della società stessa.</span><span class="sxs-lookup"><span data-stu-id="4119a-120">Then add the registry values to your company's key.</span></span>

<span data-ttu-id="4119a-121">Durante la lettura del Registro di sistema da un'applicazione Web, l'utente corrente dipende dall'autenticazione e dalla rappresentazione implementate nell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="4119a-121">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>

<span data-ttu-id="4119a-122">È più sicuro scrivere i dati nella cartella dell'utente (<xref:Microsoft.Win32.Registry.CurrentUser>) anziché nel computer locale (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="4119a-122">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>

<span data-ttu-id="4119a-123">Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già.</span><span class="sxs-lookup"><span data-stu-id="4119a-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="4119a-124">È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="4119a-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="4119a-125">I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi.</span><span class="sxs-lookup"><span data-stu-id="4119a-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="4119a-126">Per evitare che ciò accada, usare il metodo <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="4119a-126">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="4119a-127">Restituisce `Nothing` se la chiave non esiste.</span><span class="sxs-lookup"><span data-stu-id="4119a-127">It returns `Nothing` if the key does not already exist.</span></span>

<span data-ttu-id="4119a-128">Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="4119a-128">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>

<span data-ttu-id="4119a-129">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="4119a-129">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="4119a-130">Il nome della chiave è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4119a-130">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="4119a-131">L'utente non è autorizzato a creare le chiavi del Registro di sistema (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4119a-131">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="4119a-132">Il nome della chiave supera il limite di 255 caratteri (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4119a-132">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="4119a-133">La chiave è chiusa (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4119a-133">The key is closed (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="4119a-134">La chiave del Registro di sistema è di sola lettura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="4119a-134">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="4119a-135">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4119a-135">.NET Framework Security</span></span>

<span data-ttu-id="4119a-136">Per eseguire questo processo, l'assembly richiede un livello di privilegio concesso dalla classe <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="4119a-136">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="4119a-137">Se viene eseguito in un contesto parzialmente attendibile, il processo potrebbe generare un'eccezione a causa di privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="4119a-137">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="4119a-138">Allo stesso modo, l'utente deve disporre degli ACL corretti per la creazione o la scrittura nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4119a-138">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="4119a-139">Ad esempio, un'applicazione locale che ha l'autorizzazione di sicurezza dall'accesso di codice potrebbe non avere l'autorizzazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4119a-139">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="4119a-140">Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="4119a-140">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4119a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4119a-141">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [<span data-ttu-id="4119a-142">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4119a-142">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="4119a-143">Nozioni fondamentali sulla sicurezza per l’accesso al codice</span><span class="sxs-lookup"><span data-stu-id="4119a-143">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
