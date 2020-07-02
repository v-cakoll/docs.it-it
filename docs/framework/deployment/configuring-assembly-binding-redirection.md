---
title: Configurazione del reindirizzamento dell'associazione di assembly
description: Vedere come configurare il reindirizzamento dell'associazione di assembly in .NET usando l'attributo appliesTo nell'elemento assembly di un file di configurazione dell'applicazione.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: 8f3e2270d92e11ea467d6cefc2b19b4faff563b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621730"
---
# <a name="configuring-assembly-binding-redirection"></a><span data-ttu-id="03367-103">Configurazione del reindirizzamento dell'associazione di assembly</span><span class="sxs-lookup"><span data-stu-id="03367-103">Configuring Assembly Binding Redirection</span></span>
<span data-ttu-id="03367-104">Per impostazione predefinita, le applicazioni usano l'insieme di assembly .NET Framework fornito con la versione di runtime usata per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="03367-104">By default, applications use the set of .NET Framework assemblies that shipped with the runtime version used to compile the application.</span></span> <span data-ttu-id="03367-105">È possibile usare l'attributo **appliesTo** [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) nell'elemento in un file di configurazione dell'applicazione per reindirizzare i riferimenti di associazione di assembly a una versione specifica degli assembly di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03367-105">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an application configuration file to redirect assembly binding references to a specific version of the .NET Framework assemblies.</span></span> <span data-ttu-id="03367-106">Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="03367-106">This optional attribute uses a .NET Framework version number to indicate which version it applies to.</span></span> <span data-ttu-id="03367-107">Se non è specificato alcun attributo **appliesTo** , l' **\<assemblyBinding>** elemento si applica a tutte le versioni del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03367-107">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="03367-108">L'attributo **appliesTo** è stato introdotto in .NET Framework versione 1.1 e viene ignorato dalla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="03367-108">The **appliesTo** attribute was introduced in the .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="03367-109">Ciò significa che tutti **\<assemblyBinding>** gli elementi vengono applicati quando si usa la versione di .NET Framework 1,0, anche se viene specificato un attributo **appliesTo** .</span><span class="sxs-lookup"><span data-stu-id="03367-109">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03367-110">Usare l'attributo **appliesTo** per limitare il reindirizzamento dell'associazione di assembly a una specifica versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="03367-110">Use the **appliesTo** attribute to limit assembly binding redirection to a specific version of the runtime.</span></span>  
  
 <span data-ttu-id="03367-111">Ad esempio, per reindirizzare un'associazione di assembly per un assembly di .NET Framework versione 1.0, è necessario includere il codice XML seguente nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="03367-111">For example, to redirect assembly binding for a .NET Framework version 1.0 assembly, you would include the following XML code in your application configuration file.</span></span>  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="03367-112">Gli **\<assemblyBinding>** elementi sono sensibili agli ordini.</span><span class="sxs-lookup"><span data-stu-id="03367-112">The **\<assemblyBinding>** elements are order-sensitive.</span></span> <span data-ttu-id="03367-113">È necessario immettere prima le informazioni di reindirizzamento di associazione di assembly per gli assembly di .NET Framework versione 1.0, poi le informazioni di reindirizzamento di associazione di assembly per gli assembly di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="03367-113">You should enter assembly binding redirection information for any .NET Framework version 1.0 assemblies first, followed by assembly binding redirection information for any .NET Framework version 1.1 assemblies.</span></span> <span data-ttu-id="03367-114">Immettere infine le informazioni di reindirizzamento dell'binding di assembly per qualsiasi reindirizzamento di assembly .NET Framework in cui non viene usato l'attributo **appliesTo** e che quindi viene applicato a tutte le versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03367-114">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="03367-115">In caso di conflitto nel reindirizzamento, verrà usata la prima istruzione di reindirizzamento corrispondente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="03367-115">In case of a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="03367-116">Per reindirizzare, ad esempio, un riferimento a un assembly di .NET Framework versione 1.0 e un altro riferimento a un assembly di .NET Framework versione 1.1, è possibile usare il modello illustrato nel frammento di codice che segue.</span><span class="sxs-lookup"><span data-stu-id="03367-116">For example, to redirect one reference to a .NET Framework version 1.0 assembly and another reference to a .NET Framework version 1.1 assembly, you would use the pattern shown in the following pseudocode.</span></span>  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">
  <!-- .NET Framework version 1.0 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">
  <!-- .NET Framework version 1.1 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="...">
  <!-- Redirects meant for all versions of the .NET Framework. -->
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a><span data-ttu-id="03367-117">Debug degli errori del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="03367-117">Debugging Configuration File Errors</span></span>  
 <span data-ttu-id="03367-118">I file di configurazione vengono analizzati nel runtime al momento della creazione di un dominio applicazione e vengono quindi caricati in tale dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="03367-118">The runtime parses configuration files once when an application domain is created, and loads code into that application domain.</span></span> <span data-ttu-id="03367-119">In Common Language Runtime, gli errori in un file di configurazione vengono gestiti ignorando la voce che genera l'errore.</span><span class="sxs-lookup"><span data-stu-id="03367-119">The common language runtime handles errors in a configuration file by ignoring the entry.</span></span> <span data-ttu-id="03367-120">Un file di configurazione contenente XML in formato non corretto viene ignorato completamente.</span><span class="sxs-lookup"><span data-stu-id="03367-120">The runtime ignores the entire configuration file if it contains malformed XML.</span></span> <span data-ttu-id="03367-121"> In caso di codice XML non valido, verranno ignorate solo le sezioni non valide.</span><span class="sxs-lookup"><span data-stu-id="03367-121">For invalid XML, only the invalid sections are ignored.</span></span>  
  
 <span data-ttu-id="03367-122">È possibile determinare se un file di configurazione viene usato determinando se si verificano reindirizzamenti dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="03367-122">You can determine whether a configuration file is being used by determining whether assembly binding redirects are occurring.</span></span> <span data-ttu-id="03367-123">Per visualizzare gli assembly caricati usare [Fuslogvw.exe (Visualizzatore log associazioni assembly)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="03367-123">Use the [Assembly Binding Log Viewer (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to see which assemblies are being loaded.</span></span> <span data-ttu-id="03367-124">Per visualizzare tutte le associazioni di assembly è necessario impostare una voce per **ForceLog** nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="03367-124">To see all assembly binds, you must set an entry for **ForceLog** in the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03367-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03367-125">See also</span></span>

- [<span data-ttu-id="03367-126">Procedura: Abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="03367-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
