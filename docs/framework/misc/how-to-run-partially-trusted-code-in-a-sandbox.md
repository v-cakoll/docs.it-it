---
title: 'Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox'
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: b2f5a72e747f6c71743a7b22fe9f1962ac2f6b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181185"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a><span data-ttu-id="6c3d8-102">Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="6c3d8-102">How to: Run Partially Trusted Code in a Sandbox</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="6c3d8-103">Il termine sandboxing si riferisce all'esecuzione di codice in un ambiente di sicurezza con restrizioni che limita le autorizzazioni di accesso concesse al codice.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-103">Sandboxing is the practice of running code in a restricted security environment, which limits the access permissions granted to the code.</span></span> <span data-ttu-id="6c3d8-104">Se, ad esempio, si dispone di una libreria gestita proveniente da un'origine non considerata completamente attendibile, è consigliabile non eseguirla come completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-104">For example, if you have a managed library from a source you do not completely trust, you should not run it as fully trusted.</span></span> <span data-ttu-id="6c3d8-105">Inserire invece il codice in un ambiente sandbox che limita le autorizzazioni a quelle che si prevede siano necessarie (ad esempio, l'autorizzazione <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).</span><span class="sxs-lookup"><span data-stu-id="6c3d8-105">Instead, you should place the code in a sandbox that limits its permissions to those that you expect it to need (for example, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission).</span></span>  
  
 <span data-ttu-id="6c3d8-106">È anche possibile usare il sandboxing per testare il codice da distribuire che verrà eseguito in ambienti parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-106">You can also use sandboxing to test code you will be distributing that will run in partially trusted environments.</span></span>  
  
 <span data-ttu-id="6c3d8-107">Un oggetto <xref:System.AppDomain> costituisce un modo efficace per fornire un ambiente sandbox per le applicazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-107">An <xref:System.AppDomain> is an effective way of providing a sandbox for managed applications.</span></span> <span data-ttu-id="6c3d8-108">I domini applicazione usati per l'esecuzione di codice parzialmente attendibile dispongono di autorizzazioni che definiscono le risorse protette disponibili durante l'esecuzione in <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-108">Application domains that are used for running partially trusted code have permissions that define the protected resources that are available when running within that <xref:System.AppDomain>.</span></span> <span data-ttu-id="6c3d8-109">Il codice eseguito in <xref:System.AppDomain> è vincolato dalle autorizzazioni associate a <xref:System.AppDomain> e può accedere solo alle risorse specificate.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-109">Code that runs inside the <xref:System.AppDomain> is bound by the permissions associated with the <xref:System.AppDomain> and is allowed to access only the specified resources.</span></span> <span data-ttu-id="6c3d8-110"><xref:System.AppDomain> include anche una matrice <xref:System.Security.Policy.StrongName> usata per identificare gli assembly da caricare come completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-110">The <xref:System.AppDomain> also includes a <xref:System.Security.Policy.StrongName> array that is used to identify assemblies that are to be loaded as fully trusted.</span></span> <span data-ttu-id="6c3d8-111">In questo modo, il creatore di un oggetto <xref:System.AppDomain> può avviare un nuovo dominio in modalità sandbox tramite cui gli assembly helper vengono considerati completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-111">This enables the creator of an <xref:System.AppDomain> to start a new sandboxed domain that allows specific helper assemblies to be fully trusted.</span></span> <span data-ttu-id="6c3d8-112">Un'altra opzione per il caricamento degli assembly come completamente attendibili consiste nel collocarli nella Global Assembly Cache. In questo modo, tuttavia, gli assembly verranno caricati come completamente attendibili in tutti i domini applicazione creati in tale computer.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-112">Another option for loading assemblies as fully trusted is to place them in the global assembly cache; however, that will load assemblies as fully trusted in all application domains created on that computer.</span></span> <span data-ttu-id="6c3d8-113">L'elenco di nomi sicuri consente di prendere una decisione per ogni oggetto <xref:System.AppDomain>, offrendo quindi caratteristiche più restrittive.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-113">The list of strong names supports a per-<xref:System.AppDomain> decision that provides more restrictive determination.</span></span>  
  
 <span data-ttu-id="6c3d8-114">È possibile usare l'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> per specificare il set di autorizzazioni per le applicazioni eseguite in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-114">You can use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> method overload to specify the permission set for applications that run in a sandbox.</span></span> <span data-ttu-id="6c3d8-115">Questo overload consente di specificare il livello esatto di sicurezza dall'accesso di codice desiderato.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-115">This overload enables you to specify the exact level of code access security you want.</span></span> <span data-ttu-id="6c3d8-116">Gli assembly caricati in un oggetto <xref:System.AppDomain> usando questo overload possono solo disporre del set di autorizzazioni specificato o essere considerati completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-116">Assemblies that are loaded into an <xref:System.AppDomain> by using this overload can either have the specified grant set only, or can be fully trusted.</span></span> <span data-ttu-id="6c3d8-117">L'assembly viene considerato completamente attendibile se è presente nella Global Assembly Cache o elencato nel parametro della matrice `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>).</span><span class="sxs-lookup"><span data-stu-id="6c3d8-117">The assembly is granted full trust if it is in the global assembly cache or listed in the `fullTrustAssemblies` (the <xref:System.Security.Policy.StrongName>) array parameter.</span></span> <span data-ttu-id="6c3d8-118">Solo gli assembly completamente attendibili devono essere aggiunti all'elenco `fullTrustAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-118">Only assemblies known to be fully trusted should be added to the `fullTrustAssemblies` list.</span></span>  
  
 <span data-ttu-id="6c3d8-119">L'overload ha la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-119">The overload has the following signature:</span></span>  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 <span data-ttu-id="6c3d8-120">I parametri per l'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> specificano il nome di <xref:System.AppDomain>, l'evidenza per <xref:System.AppDomain>, l'oggetto <xref:System.AppDomainSetup> che identifica la base dell'applicazione per l'ambiente sandbox, il set di autorizzazioni da usare e i nomi sicuri per gli assembly completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-120">The parameters for the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload specify the name of the <xref:System.AppDomain>, the evidence for the <xref:System.AppDomain>, the <xref:System.AppDomainSetup> object that identifies the application base for the sandbox, the permission set to use, and the strong names for fully trusted assemblies.</span></span>  
  
 <span data-ttu-id="6c3d8-121">Per motivi di sicurezza, la base dell'applicazione specificata nel parametro `info` non deve corrispondere alla base dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-121">For security reasons, the application base specified in the `info` parameter should not be the application base for the hosting application.</span></span>  
  
 <span data-ttu-id="6c3d8-122">Per il parametro `grantSet`, è possibile specificare un set di autorizzazioni creato in modo esplicito o un set di autorizzazioni standard creato dal metodo <xref:System.Security.SecurityManager.GetStandardSandbox%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-122">For the `grantSet` parameter, you can specify either a permission set you have explicitly created, or a standard permission set created by the <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method.</span></span>  
  
 <span data-ttu-id="6c3d8-123">A differenza della maggior parte dei caricamenti di <xref:System.AppDomain>, l'evidenza per <xref:System.AppDomain> (fornita dal parametro `securityInfo`) non viene usata per determinare il set di autorizzazioni per gli assembly parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-123">Unlike most <xref:System.AppDomain> loads, the evidence for the <xref:System.AppDomain> (which is provided by the `securityInfo` parameter) is not used to determine the grant set for the partially trusted assemblies.</span></span> <span data-ttu-id="6c3d8-124">Viene invece specificata in modo indipendente dal parametro `grantSet`.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-124">Instead, it is independently specified by the `grantSet` parameter.</span></span> <span data-ttu-id="6c3d8-125">L'evidenza può essere usata per altri scopi, ad esempio per determinare l'ambito dello spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-125">However, the evidence can be used for other purposes such as determining the isolated storage scope.</span></span>  
  
### <a name="to-run-an-application-in-a-sandbox"></a><span data-ttu-id="6c3d8-126">Per eseguire un'applicazione in un ambiente sandbox</span><span class="sxs-lookup"><span data-stu-id="6c3d8-126">To run an application in a sandbox</span></span>  
  
1. <span data-ttu-id="6c3d8-127">Creare il set di autorizzazioni da concedere all'applicazione non attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-127">Create the permission set to be granted to the untrusted application.</span></span> <span data-ttu-id="6c3d8-128">L'autorizzazione minima che è possibile concedere è <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-128">The minimum permission you can grant is <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span> <span data-ttu-id="6c3d8-129">È anche possibile concedere autorizzazioni aggiuntive che si ritengono sicure per il codice non attendibile, ad esempio <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-129">You can also grant additional permissions you think might be safe for untrusted code; for example, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span></span> <span data-ttu-id="6c3d8-130">Il codice seguente crea un nuovo set di autorizzazioni con solo l'autorizzazione <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-130">The following code creates a new permission set with only <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span>  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     <span data-ttu-id="6c3d8-131">In alternativa, è possibile usare un set di autorizzazioni denominato esistente, ad esempio Internet.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-131">Alternatively, you can use an existing named permission set, such as Internet.</span></span>  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     <span data-ttu-id="6c3d8-132">Il metodo <xref:System.Security.SecurityManager.GetStandardSandbox%2A> restituisce un set di autorizzazioni `Internet` o un set di autorizzazioni `LocalIntranet`, a seconda dell'area nell'evidenza.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-132">The <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method returns either an `Internet` permission set or a `LocalIntranet` permission set depending on the zone in the evidence.</span></span> <span data-ttu-id="6c3d8-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> crea inoltre autorizzazioni di identità per alcuni degli oggetti evidenza passati come riferimenti.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> also constructs identity permissions for some of the evidence objects passed as references.</span></span>  
  
2. <span data-ttu-id="6c3d8-134">Firmare l'assembly contenente la classe host (in questo esempio `Sandboxer`) che chiama il codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-134">Sign the assembly that contains the hosting class (named `Sandboxer` in this example) that calls the untrusted code.</span></span> <span data-ttu-id="6c3d8-135">Aggiungere l'oggetto <xref:System.Security.Policy.StrongName> usato per firmare l'assembly alla matrice <xref:System.Security.Policy.StrongName> del parametro `fullTrustAssemblies` della chiamata a <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-135">Add the <xref:System.Security.Policy.StrongName> used to sign the assembly to the <xref:System.Security.Policy.StrongName> array of the `fullTrustAssemblies` parameter of the <xref:System.AppDomain.CreateDomain%2A> call.</span></span> <span data-ttu-id="6c3d8-136">La classe host deve essere eseguita come completamente attendibile per consentire l'esecuzione del codice parzialmente attendibile o per offrire servizi per l'applicazione parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-136">The hosting class must run as fully trusted to enable the execution of the partial-trust code or to offer services to the partial-trust application.</span></span> <span data-ttu-id="6c3d8-137">Ecco come viene letto l'oggetto <xref:System.Security.Policy.StrongName> di un assembly:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-137">This is how you read the <xref:System.Security.Policy.StrongName> of an assembly:</span></span>  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     <span data-ttu-id="6c3d8-138">Non è necessario aggiungere gli assembly .NET Framework, come mscorlib e System. dll, all'elenco di elementi completamente attendibili, in quanto vengono caricati come completamente attendibili dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-138">.NET Framework assemblies such as mscorlib and System.dll do not have to be added to the full-trust list because they are loaded as fully trusted from the global assembly cache.</span></span>  
  
3. <span data-ttu-id="6c3d8-139">Inizializzare il parametro <xref:System.AppDomainSetup> del metodo <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-139">Initialize the <xref:System.AppDomainSetup> parameter of the <xref:System.AppDomain.CreateDomain%2A> method.</span></span> <span data-ttu-id="6c3d8-140">Con questo parametro, è possibile controllare numerose impostazioni del nuovo oggetto <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-140">With this parameter, you can control many of the settings of the new <xref:System.AppDomain>.</span></span> <span data-ttu-id="6c3d8-141">La proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> è un'impostazione importante e deve essere diversa dalla proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> per l'oggetto <xref:System.AppDomain> dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-141">The <xref:System.AppDomainSetup.ApplicationBase%2A> property is an important setting, and should be different from the <xref:System.AppDomainSetup.ApplicationBase%2A> property for the <xref:System.AppDomain> of the hosting application.</span></span> <span data-ttu-id="6c3d8-142">Se le impostazioni di <xref:System.AppDomainSetup.ApplicationBase%2A> corrispondono, l'applicazione parzialmente attendibile può fare in modo che l'applicazione host carichi (come completamente attendibile) un'eccezione definita, che può quindi essere sfruttata.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-142">If the <xref:System.AppDomainSetup.ApplicationBase%2A> settings are the same, the partial-trust application can get the hosting application to load (as fully trusted) an exception it defines, thus exploiting it.</span></span> <span data-ttu-id="6c3d8-143">Questo è un altro motivo per cui non è consigliabile l'uso di un elemento catch (eccezione).</span><span class="sxs-lookup"><span data-stu-id="6c3d8-143">This is another reason why a catch (exception) is not recommended.</span></span> <span data-ttu-id="6c3d8-144">Impostando la base dell'applicazione dell'host in modo diverso dalla base dell'applicazione in modalità sandbox, è possibile ridurre il rischio di exploit.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-144">Setting the application base of the host differently from the application base of the sandboxed application mitigates the risk of exploits.</span></span>  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. <span data-ttu-id="6c3d8-145">Chiamare l'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> per creare il dominio dell'applicazione usando i parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-145">Call the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload to create the application domain using the parameters we have specified.</span></span>  
  
     <span data-ttu-id="6c3d8-146">La firma per il metodo è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-146">The signature for this method is:</span></span>  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     <span data-ttu-id="6c3d8-147">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-147">Additional information:</span></span>  
  
    - <span data-ttu-id="6c3d8-148">Questo è l'unico overload del metodo <xref:System.AppDomain.CreateDomain%2A> che accetta un oggetto <xref:System.Security.PermissionSet> come parametro e pertanto l'unico overload che consente di caricare un'applicazione con un'impostazione di attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-148">This is the only overload of the <xref:System.AppDomain.CreateDomain%2A> method that takes a <xref:System.Security.PermissionSet> as a parameter, and thus the only overload that lets you load an application in a partial-trust setting.</span></span>  
  
    - <span data-ttu-id="6c3d8-149">Il parametro `evidence` non viene usato per calcolare un set di autorizzazioni, ma per l'identificazione da parte di altre funzionalità di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-149">The `evidence` parameter is not used to calculate a permission set; it is used for identification by other features of the .NET Framework.</span></span>  
  
    - <span data-ttu-id="6c3d8-150">L'impostazione della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> del parametro `info` è obbligatoria per questo overload.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-150">Setting the <xref:System.AppDomainSetup.ApplicationBase%2A> property of the `info` parameter is mandatory for this overload.</span></span>  
  
    - <span data-ttu-id="6c3d8-151">Il parametro `fullTrustAssemblies` dispone della parola chiave `params`, pertanto non è necessario creare una matrice <xref:System.Security.Policy.StrongName>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-151">The `fullTrustAssemblies` parameter has the `params` keyword, which means that it is not necessary to create a <xref:System.Security.Policy.StrongName> array.</span></span> <span data-ttu-id="6c3d8-152">È possibile passare 0, 1 o più nomi sicuri come parametri.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-152">Passing 0, 1, or more strong names as parameters is allowed.</span></span>  
  
    - <span data-ttu-id="6c3d8-153">Il codice per creare il dominio applicazione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-153">The code to create the application domain is:</span></span>  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. <span data-ttu-id="6c3d8-154">Caricare il codice nell'oggetto <xref:System.AppDomain> sandbox creato.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-154">Load the code into the sandboxing <xref:System.AppDomain> that you created.</span></span> <span data-ttu-id="6c3d8-155">A questo scopo, è possibile eseguire una delle due operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-155">This can be done in two ways:</span></span>  
  
    - <span data-ttu-id="6c3d8-156">Chiamare il metodo <xref:System.AppDomain.ExecuteAssembly%2A> per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-156">Call the <xref:System.AppDomain.ExecuteAssembly%2A> method for the assembly.</span></span>  
  
    - <span data-ttu-id="6c3d8-157">Usare il metodo <xref:System.Activator.CreateInstanceFrom%2A> per creare un'istanza di una classe derivata da <xref:System.MarshalByRefObject> nel nuovo oggetto <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-157">Use the <xref:System.Activator.CreateInstanceFrom%2A> method to create an instance of a class derived from <xref:System.MarshalByRefObject> in the new <xref:System.AppDomain>.</span></span>  
  
     <span data-ttu-id="6c3d8-158">Il secondo metodo è preferibile, in quanto consente di passare in modo più semplice i parametri alla nuova istanza di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-158">The second method is preferable, because it makes it easier to pass parameters to the new <xref:System.AppDomain> instance.</span></span> <span data-ttu-id="6c3d8-159">Il metodo <xref:System.Activator.CreateInstanceFrom%2A> offre due funzionalità importanti:</span><span class="sxs-lookup"><span data-stu-id="6c3d8-159">The <xref:System.Activator.CreateInstanceFrom%2A> method provides two important features:</span></span>  
  
    - <span data-ttu-id="6c3d8-160">È possibile usare una codebase che punta a una posizione che non contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-160">You can use a code base that points to a location that does not contain your assembly.</span></span>  
  
    - <span data-ttu-id="6c3d8-161">È possibile eseguire la creazione in un oggetto <xref:System.Security.CodeAccessPermission.Assert%2A> per l'attendibilità totale (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), per poter creare un'istanza di una classe critica.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-161">You can do the creation under an <xref:System.Security.CodeAccessPermission.Assert%2A> for full-trust (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), which enables you to create an instance of a critical class.</span></span> <span data-ttu-id="6c3d8-162">(Questo accade ogni volta che l'assieme non ha segni di trasparenza e viene caricato come completamente attendibile.) Pertanto, è necessario prestare attenzione a creare solo codice attendibile con questa funzione ed è consigliabile creare solo istanze di classi completamente attendibili nel nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-162">(This happens whenever your assembly has no transparency markings and is loaded as fully trusted.) Therefore, you have to be careful to create only code that you trust with this function, and we recommend that you create only instances of fully trusted classes in the new application domain.</span></span>  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     <span data-ttu-id="6c3d8-163">Si noti che per creare un'istanza di una classe in un nuovo dominio, la classe deve estendere la classe <xref:System.MarshalByRefObject>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-163">Note that in order to create an instance of a class in a new domain, the class has to extend the <xref:System.MarshalByRefObject> class</span></span>  
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. <span data-ttu-id="6c3d8-164">Annullare il wrapping dell'istanza del nuovo dominio in un riferimento in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-164">Unwrap the new domain instance into a reference in this domain.</span></span> <span data-ttu-id="6c3d8-165">Questo riferimento viene usato per eseguire codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-165">This reference is used to execute the untrusted code.</span></span>  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. <span data-ttu-id="6c3d8-166">Chiamare il metodo `ExecuteUntrustedCode` nell'istanza della classe `Sandboxer` appena creata.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-166">Call the `ExecuteUntrustedCode` method in the instance of the `Sandboxer` class you just created.</span></span>  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     <span data-ttu-id="6c3d8-167">Questa chiamata viene eseguita nel dominio applicazione in modalità sandbox, con autorizzazioni limitate.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-167">This call is executed in the sandboxed application domain, which has restricted permissions.</span></span>  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <span data-ttu-id="6c3d8-168">Viene usato <xref:System.Reflection> per ottenere un handle di un metodo nell'assembly parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-168"><xref:System.Reflection> is used to get a handle of a method in the partially trusted assembly.</span></span> <span data-ttu-id="6c3d8-169">L'handle può essere usato per eseguire codice in modo sicuro con autorizzazioni minime.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-169">The handle can be used to execute code in a safe way with minimum permissions.</span></span>  
  
     <span data-ttu-id="6c3d8-170">Nel codice precedente, osservare l'oggetto <xref:System.Security.PermissionSet.Assert%2A> per l'autorizzazione di attendibilità totale prima di stampare <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-170">In the previous code, note the <xref:System.Security.PermissionSet.Assert%2A> for the full-trust permission before printing the <xref:System.Security.SecurityException>.</span></span>  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     <span data-ttu-id="6c3d8-171">L'asserzione di attendibilità totale viene usata per ottenere informazioni estese da <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-171">The full-trust assert is used to obtain extended information from the <xref:System.Security.SecurityException>.</span></span> <span data-ttu-id="6c3d8-172">Senza l'oggetto <xref:System.Security.PermissionSet.Assert%2A>, il metodo <xref:System.Security.SecurityException.ToString%2A> di <xref:System.Security.SecurityException> individuerebbe la presenza di codice parzialmente attendibile nello stack e limiterebbe le informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-172">Without the <xref:System.Security.PermissionSet.Assert%2A>, the <xref:System.Security.SecurityException.ToString%2A> method of <xref:System.Security.SecurityException> will discover that there is partially trusted code on the stack and will restrict the information returned.</span></span> <span data-ttu-id="6c3d8-173">Ciò potrebbe causare problemi di sicurezza se il codice parzialmente attendibile potesse leggere tali informazioni, ma i rischi vengono attenuati non concedendo <xref:System.Security.Permissions.UIPermission>.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-173">This could cause security issues if the partial-trust code could read that information, but the risk is mitigated by not granting <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="6c3d8-174">L'asserzione di attendibilità totale deve essere usata con cautela e solo quando si è certi di non consentire l'elevazione di codice parzialmente attendibile a codice completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-174">The full-trust assert should be used sparingly and only when you are sure that you are not allowing partial-trust code to elevate to full trust.</span></span> <span data-ttu-id="6c3d8-175">Di norma, non chiamare codice non considerato attendibile nella stessa funzione e dopo avere chiamato un'asserzione di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-175">As a rule, do not call code you do not trust in the same function and after you called an assert for full trust.</span></span> <span data-ttu-id="6c3d8-176">È consigliabile annullare sempre l'asserzione dopo averla usata.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-176">It is good practice to always revert the assert when you have finished using it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c3d8-177">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c3d8-177">Example</span></span>  
 <span data-ttu-id="6c3d8-178">Nell'esempio seguente viene implementata la procedura della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-178">The following example implements the procedure in the previous section.</span></span> <span data-ttu-id="6c3d8-179">Nell'esempio un progetto denominato `Sandboxer` in una soluzione di Visual Studio contiene un progetto denominato `UntrustedCode`, che implementa la classe `UntrustedClass`.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-179">In the example, a project named `Sandboxer` in a Visual Studio solution also contains a project named `UntrustedCode`, which implements the class `UntrustedClass`.</span></span> <span data-ttu-id="6c3d8-180">Questo scenario presuppone che sia stato scaricato un assembly di librerie contenente un metodo che restituisce `true` o `false` per indicare se il numero fornito è un numero di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-180">This scenario assumes that you have downloaded a library assembly containing a method that is expected to return `true` or `false` to indicate whether the number you provided is a Fibonacci number.</span></span> <span data-ttu-id="6c3d8-181">Il metodo tenta invece di leggere un file dal computer.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-181">Instead, the method attempts to read a file from your computer.</span></span> <span data-ttu-id="6c3d8-182">L'esempio seguente mostra il codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-182">The following example shows the untrusted code.</span></span>  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="6c3d8-183">L'esempio seguente mostra il codice dell'applicazione `Sandboxer` che esegue il codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="6c3d8-183">The following example shows the `Sandboxer` application code that executes the untrusted code.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c3d8-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c3d8-184">See also</span></span>

- [<span data-ttu-id="6c3d8-185">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="6c3d8-185">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
