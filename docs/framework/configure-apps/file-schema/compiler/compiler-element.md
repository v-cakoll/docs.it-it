---
title: '&lt;compilatore&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2ef50301a5188193cc13cd0e657f53593ef0d93e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="5e8b1-102">&lt;compilatore&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="5e8b1-103">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="5e8b1-104">\<Elemento di configurazione ></span><span class="sxs-lookup"><span data-stu-id="5e8b1-104">\<configuration Element></span></span>  
<span data-ttu-id="5e8b1-105">\<Elemento System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="5e8b1-105">\<system.codedom Element></span></span>  
<span data-ttu-id="5e8b1-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="5e8b1-106">\<compilers Element></span></span>  
<span data-ttu-id="5e8b1-107">\<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8b1-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e8b1-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e8b1-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5e8b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5e8b1-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e8b1-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="5e8b1-111">Attributes</span></span>  
  
|<span data-ttu-id="5e8b1-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="5e8b1-112">Attribute</span></span>|<span data-ttu-id="5e8b1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e8b1-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="5e8b1-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5e8b1-115">Specifica ulteriori argomenti specifici del compilatore per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="5e8b1-116">I valori per il `compilerOptions` attributo sono in genere elencati in un argomento di opzioni del compilatore per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="5e8b1-117">Nella documentazione di Visual Studio 2005, è possibile individuare le opzioni del compilatore cercando "opzioni del compilatore" nell'indice.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="5e8b1-118">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e8b1-119">Fornisce un elenco delimitato da punto e virgola di estensioni di file utilizzato dai file di origine per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="5e8b1-120">Ad esempio, "cs".</span><span class="sxs-lookup"><span data-stu-id="5e8b1-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="5e8b1-121">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e8b1-122">Fornisce un elenco delimitato da punto e virgola di nomi della lingua supportate dal provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="5e8b1-123">Ad esempio, "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="5e8b1-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="5e8b1-124">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e8b1-125">Specifica il nome del tipo di provider del linguaggio, inclusi il nome dell'assembly contenente l'implementazione del provider.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="5e8b1-126">Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="5e8b1-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="5e8b1-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5e8b1-128">Specifica il livello di avviso del compilatore predefinito; Determina il livello in corrispondenza del quale il provider del linguaggio considera gli avvisi di compilazione come errori.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e8b1-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5e8b1-129">Child Elements</span></span>  
  
|<span data-ttu-id="5e8b1-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-130">Element</span></span>|<span data-ttu-id="5e8b1-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e8b1-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e8b1-132">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="5e8b1-133">Specifica gli attributi di versione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e8b1-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5e8b1-134">Parent Elements</span></span>  
  
|<span data-ttu-id="5e8b1-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-135">Element</span></span>|<span data-ttu-id="5e8b1-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e8b1-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e8b1-137">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="5e8b1-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="5e8b1-138">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="5e8b1-139">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="5e8b1-140">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="5e8b1-141">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="5e8b1-142">Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e8b1-143">Note</span><span class="sxs-lookup"><span data-stu-id="5e8b1-143">Remarks</span></span>  
 <span data-ttu-id="5e8b1-144">Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="5e8b1-145">Estende il provider di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico; il `<compiler>` elemento definisce il compilatore e le impostazioni del generatore di codice per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="5e8b1-146">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5e8b1-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="5e8b1-147">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="5e8b1-148">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="5e8b1-149">Elementi del compilatore all'applicazione o un file di configurazione Web possono integrare o sostituire le impostazioni nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="5e8b1-150">Se più di un'implementazione del provider è configurata per lo stesso nome di lingua o la stessa estensione, l'ultima configurazione corrispondente esegue l'override di qualsiasi provider precedentemente configurato per tale estensione di file o nome di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5e8b1-151">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5e8b1-151">Configuration File</span></span>  
 <span data-ttu-id="5e8b1-152">Questo elemento può essere usato nel file di configurazione del computer e i file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e8b1-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e8b1-153">Example</span></span>  
 <span data-ttu-id="5e8b1-154">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="5e8b1-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e8b1-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e8b1-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="5e8b1-156">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="5e8b1-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="5e8b1-157">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="5e8b1-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 <span data-ttu-id="5e8b1-158">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="5e8b1-158">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>  
 [<span data-ttu-id="5e8b1-159">compilatore elemento per i compilatori per compilation (Schema delle impostazioni ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="5e8b1-159">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
