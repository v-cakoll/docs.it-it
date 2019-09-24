---
title: 'Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35bf61ffd2a85221cdf33a0304765d94770c1eab
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053981"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a><span data-ttu-id="28520-102">Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro</span><span class="sxs-lookup"><span data-stu-id="28520-102">How to: Disable the strong-name bypass feature</span></span>
<span data-ttu-id="28520-103">A partire da .NET Framework versione 3.5 Service Pack 1 (SP1), le firme con nome sicuro non vengono convalidate quando un assembly viene caricato in un oggetto <xref:System.AppDomain> con attendibilità totale, ad esempio l'oggetto predefinito <xref:System.AppDomain> per la zona `MyComputer`.</span><span class="sxs-lookup"><span data-stu-id="28520-103">Starting with the .NET Framework version 3.5 Service Pack 1 (SP1), strong-name signatures are not validated when an assembly is loaded into a full-trust <xref:System.AppDomain> object, such as the default <xref:System.AppDomain> for the `MyComputer` zone.</span></span> <span data-ttu-id="28520-104">Questo comportamento è reso possibile dalla funzionalità che consente di ignorare la verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="28520-104">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="28520-105">In un ambiente ad attendibilità totale le richieste di <xref:System.Security.Permissions.StrongNameIdentityPermission> hanno sempre esito positivo per gli assembly ad attendibilità totale firmati, indipendentemente dalla firma.</span><span class="sxs-lookup"><span data-stu-id="28520-105">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies regardless of their signature.</span></span> <span data-ttu-id="28520-106">L'unica restrizione è che l'assembly deve essere ad attendibilità totale perché la relativa area è ad attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="28520-106">The only restriction is that the assembly must be fully trusted because its zone is fully trusted.</span></span> <span data-ttu-id="28520-107">Poiché il nome sicuro non è un fattore determinante in queste condizioni, non esiste alcun motivo per cui venga validato.</span><span class="sxs-lookup"><span data-stu-id="28520-107">Because the strong name is not a determining factor under these conditions, there is no reason for it to be validated.</span></span> <span data-ttu-id="28520-108">Se la convalida di firme con nome sicuro viene ignorata, si ottengono miglioramenti significativi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="28520-108">Bypassing the validation of strong-name signatures provides significant performance improvements.</span></span>  
  
 <span data-ttu-id="28520-109">La funzionalità che consente di ignorare il nome sicuro si applica a qualsiasi assembly ad attendibilità totale che non abbia la firma ritardata e che sia caricato in un oggetto <xref:System.AppDomain> ad attendibilità totale dalla directory specificata dalla proprietà <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="28520-109">The bypass feature applies to any full-trust assembly that is not delay-signed and that is loaded into any full-trust <xref:System.AppDomain> from the directory specified by its <xref:System.AppDomainSetup.ApplicationBase%2A> property.</span></span>  
  
 <span data-ttu-id="28520-110">È possibile ignorare questa funzionalità per tutte le applicazioni di un computer impostando il valore di una chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="28520-110">You can override the bypass feature for all applications on a computer by setting a registry key value.</span></span> <span data-ttu-id="28520-111">È possibile ignorare l'impostazione per una singola applicazione usando il relativo file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="28520-111">You can override the setting for a single application by using an application configuration file.</span></span> <span data-ttu-id="28520-112">Non è possibile ripristinare questa funzionalità per una singola applicazione se è stata disabilitata tramite la chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="28520-112">You cannot reinstate the bypass feature for a single application if it has been disabled by the registry key.</span></span>  
  
 <span data-ttu-id="28520-113">Quando si ignora la funzionalità, il nome sicuro viene convalidato solo per verificare che sia corretto e non viene controllata la presenza di un oggetto <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="28520-113">When you override the bypass feature, the strong name is validated only for correctness; it is not checked for a <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span></span> <span data-ttu-id="28520-114">Se si vuole verificare un nome sicuro specifico, è necessario eseguire il controllo separatamente.</span><span class="sxs-lookup"><span data-stu-id="28520-114">If you want to confirm a specific strong name, you have to perform that check separately.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="28520-115">La possibilità per forzare la convalida del nome sicuro dipende da una chiave del Registro di sistema, come descritto nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="28520-115">The ability to force strong-name validation depends on a registry key, as described in the following procedure.</span></span> <span data-ttu-id="28520-116">Se un'applicazione è in esecuzione con un account che non ha l'autorizzazione Elenco di controllo di accesso (ACL) per l'accesso alla chiave del Registro di sistema, l'impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="28520-116">If an application is running under an account that does not have access control list (ACL) permission to access that registry key, the setting is ineffective.</span></span> <span data-ttu-id="28520-117">Assicurarsi che siano configurati diritti ACL per la chiave in modo che sia leggibile per tutti gli assembly.</span><span class="sxs-lookup"><span data-stu-id="28520-117">You must ensure that ACL rights are configured for this key so that it can be read for all assemblies.</span></span>  
  
## <a name="disable-the-strong-name-bypass-feature-for-all-applications"></a><span data-ttu-id="28520-118">Disabilitare la funzionalità di bypass con nome sicuro per tutte le applicazioni</span><span class="sxs-lookup"><span data-stu-id="28520-118">Disable the strong-name bypass feature for all applications</span></span>  
  
- <span data-ttu-id="28520-119">Nei computer a 32 bit creare nel Registro di sistema una voce DWORD con valore 0 denominata `AllowStrongNameBypass` nella chiave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework.</span><span class="sxs-lookup"><span data-stu-id="28520-119">On 32-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
- <span data-ttu-id="28520-120">Nei computer a 64 bit creare nel Registro di sistema una voce DWORD con valore 0 denominata `AllowStrongNameBypass` nelle chiavi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework e HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework.</span><span class="sxs-lookup"><span data-stu-id="28520-120">On 64-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework and HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework keys.</span></span>  
  
## <a name="disable-the-strong-name-bypass-feature-for-a-single-application"></a><span data-ttu-id="28520-121">Disabilitare la funzionalità di bypass con nome sicuro per una singola applicazione</span><span class="sxs-lookup"><span data-stu-id="28520-121">Disable the strong-name bypass feature for a single application</span></span>  
  
1. <span data-ttu-id="28520-122">Aprire o creare il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="28520-122">Open or create the application configuration file.</span></span>  
  
    <span data-ttu-id="28520-123">Per altre informazioni su questo file, vedere la sezione file di configurazione dell'applicazione in [configurare le app](../../framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="28520-123">For more information about this file, see the Application Configuration Files section in [Configure apps](../../framework/configure-apps/index.md).</span></span>  
  
2. <span data-ttu-id="28520-124">Aggiungere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="28520-124">Add the following entry:</span></span>  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 <span data-ttu-id="28520-125">È possibile ripristinare la funzionalità bypass per l'applicazione rimuovendo l'impostazione del file di configurazione o impostando l' `true`attributo su.</span><span class="sxs-lookup"><span data-stu-id="28520-125">You can restore the bypass feature for the application by removing the configuration file setting or by setting the attribute to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28520-126">È possibile attivare e disattivare la convalida dei nomi sicuri per un'applicazione solo se nel computer è attivata la funzionalità che consente di ignorare il nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="28520-126">You can turn strong-name validation on and off for an application only if the bypass feature is enabled for the computer.</span></span> <span data-ttu-id="28520-127">Se la funzionalità è stata disattivata per il computer, i nomi sicuri vengono convalidati per tutte le applicazioni e non è possibile ignorare la convalida per una singola applicazione.</span><span class="sxs-lookup"><span data-stu-id="28520-127">If the bypass feature has been turned off for the computer, strong names are validated for all applications and you cannot bypass validation for a single application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28520-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28520-128">See also</span></span>

- [<span data-ttu-id="28520-129">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="28520-129">Sn.exe (Strong Name Tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="28520-130">\<elemento > elemento bypasstrustedappstrongnames</span><span class="sxs-lookup"><span data-stu-id="28520-130">\<bypassTrustedAppStrongNames> element</span></span>](../../framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [<span data-ttu-id="28520-131">Creazione e utilizzo di assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="28520-131">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)