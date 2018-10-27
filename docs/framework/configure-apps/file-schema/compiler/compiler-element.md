---
title: '&lt;compilatore&gt; elemento'
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e8c5021b00de503783adb3f1b1dc11964639afbf
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193540"
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="b8065-102">&lt;compilatore&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-102">&lt;compiler&gt; Element</span></span>

<span data-ttu-id="b8065-103">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="b8065-104">\<Elemento Configuration > \<elemento System. CodeDom > \<compilatori elemento > \<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="b8065-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8065-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b8065-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b8065-106">Attributes and Elements</span></span>

<span data-ttu-id="b8065-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b8065-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8065-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b8065-108">Attributes</span></span>

|<span data-ttu-id="b8065-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="b8065-109">Attribute</span></span>|<span data-ttu-id="b8065-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8065-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="b8065-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b8065-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b8065-112">Specifica ulteriori argomenti specifici del compilatore per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b8065-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="b8065-113">I valori per il `compilerOptions` attributo vengono elencati in genere in un argomento relativo alle opzioni del compilatore per consentire al compilatore.</span><span class="sxs-lookup"><span data-stu-id="b8065-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="b8065-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8065-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="b8065-115">Fornisce un elenco delimitato da punto e virgola di estensioni di file usato dai file di origine per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="b8065-116">Ad esempio, "cs".</span><span class="sxs-lookup"><span data-stu-id="b8065-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="b8065-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8065-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="b8065-118">Fornisce un elenco delimitato da punto e virgola di nomi di linguaggio supportati dal provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="b8065-119">Ad esempio "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="b8065-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="b8065-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8065-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="b8065-121">Specifica il nome del tipo di provider del linguaggio, inclusi il nome dell'assembly contenente l'implementazione del provider.</span><span class="sxs-lookup"><span data-stu-id="b8065-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="b8065-122">Il nome del tipo deve soddisfare i requisiti definiti nella [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="b8065-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="b8065-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b8065-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b8065-124">Specifica il livello di avviso del compilatore predefinito; Determina il livello in corrispondenza del quale il provider del linguaggio avvisi di compilazione vengono considerati come errori.</span><span class="sxs-lookup"><span data-stu-id="b8065-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b8065-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b8065-125">Child Elements</span></span>

|<span data-ttu-id="b8065-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-126">Element</span></span>|<span data-ttu-id="b8065-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8065-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b8065-128">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-128">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="b8065-129">Specifica gli attributi di versione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b8065-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b8065-130">Parent Elements</span></span>

|<span data-ttu-id="b8065-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-131">Element</span></span>|<span data-ttu-id="b8065-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8065-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b8065-133">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="b8065-133">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b8065-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8065-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="b8065-135">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-135">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="b8065-136">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b8065-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="b8065-137">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-137">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="b8065-138">Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="b8065-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b8065-139">Note</span><span class="sxs-lookup"><span data-stu-id="b8065-139">Remarks</span></span>

<span data-ttu-id="b8065-140">Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b8065-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="b8065-141">Estende il provider di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico; il `<compiler>` elemento definisce il compilatore e le impostazioni del generatore di codice per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="b8065-142">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b8065-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="b8065-143">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="b8065-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b8065-144">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="b8065-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="b8065-145">Gli elementi del compilatore nel file di configurazione Web o applicazione possono integrare o sostituire le impostazioni nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="b8065-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="b8065-146">Se più di un'implementazione di provider è configurata per lo stesso nome di linguaggio o la stessa estensione di file, l'ultima configurazione corrisponda esegue l'override di qualsiasi provider precedentemente configurato per tale estensione di file o nome di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b8065-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="b8065-147">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b8065-147">Configuration File</span></span>

<span data-ttu-id="b8065-148">Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8065-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="b8065-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8065-149">Example</span></span>

<span data-ttu-id="b8065-150">L'esempio seguente illustra un elemento di configurazione del compilatore tipico:</span><span class="sxs-lookup"><span data-stu-id="b8065-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b8065-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8065-151">See Also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b8065-152">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b8065-152">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b8065-153">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="b8065-153">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- <span data-ttu-id="b8065-154">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="b8065-154">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>
- <span data-ttu-id="b8065-155">[Elemento Compiler per compilers per compilation (Schema delle impostazioni ASP.NET)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b8065-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span></span>
