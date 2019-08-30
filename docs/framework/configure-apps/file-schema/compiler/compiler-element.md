---
title: <compiler> Elemento
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
ms.openlocfilehash: a19cf8182cdb338fd8596ef38311916de0daae37
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168947"
---
# <a name="compiler-element"></a><span data-ttu-id="3475c-102">\<Elemento > del compilatore</span><span class="sxs-lookup"><span data-stu-id="3475c-102">\<compiler> Element</span></span>

<span data-ttu-id="3475c-103">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3475c-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[<span data-ttu-id="3475c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3475c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3475c-105">&nbsp;&nbsp;[ **\<> System. CodeDom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="3475c-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="3475c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<compilatori >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="3475c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="3475c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> del compilatore**</span><span class="sxs-lookup"><span data-stu-id="3475c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="3475c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3475c-108">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3475c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3475c-109">Attributes and Elements</span></span>

<span data-ttu-id="3475c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3475c-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3475c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="3475c-111">Attributes</span></span>

|<span data-ttu-id="3475c-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="3475c-112">Attribute</span></span>|<span data-ttu-id="3475c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3475c-113">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="3475c-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3475c-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3475c-115">Specifica argomenti aggiuntivi specifici del compilatore per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="3475c-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="3475c-116">I valori per l' `compilerOptions` attributo sono in genere elencati in un argomento delle opzioni del compilatore per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="3475c-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="3475c-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3475c-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="3475c-118">Fornisce un elenco delimitato da punti e virgola delle estensioni di file utilizzate dai file di origine per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3475c-118">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="3475c-119">Ad esempio, ". cs".</span><span class="sxs-lookup"><span data-stu-id="3475c-119">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="3475c-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3475c-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="3475c-121">Fornisce un elenco delimitato da punti e virgola di nomi di lingua supportati dal provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3475c-121">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="3475c-122">Ad esempio, "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="3475c-122">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="3475c-123">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3475c-123">Required attribute.</span></span><br /><br /> <span data-ttu-id="3475c-124">Specifica il nome del tipo del provider del linguaggio, incluso il nome dell'assembly che contiene l'implementazione del provider.</span><span class="sxs-lookup"><span data-stu-id="3475c-124">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="3475c-125">Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="3475c-125">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="3475c-126">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3475c-126">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3475c-127">Specifica il livello di avviso predefinito del compilatore. determina il livello al quale il provider del linguaggio considera gli avvisi di compilazione come errori.</span><span class="sxs-lookup"><span data-stu-id="3475c-127">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3475c-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3475c-128">Child Elements</span></span>

|<span data-ttu-id="3475c-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="3475c-129">Element</span></span>|<span data-ttu-id="3475c-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3475c-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3475c-131">\<Elemento > providerOption</span><span class="sxs-lookup"><span data-stu-id="3475c-131">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="3475c-132">Specifica gli attributi della versione del compilatore per un provider di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3475c-132">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3475c-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3475c-133">Parent Elements</span></span>

|<span data-ttu-id="3475c-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="3475c-134">Element</span></span>|<span data-ttu-id="3475c-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3475c-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3475c-136">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="3475c-136">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="3475c-137">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3475c-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="3475c-138">\<Elemento > System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="3475c-138">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="3475c-139">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="3475c-139">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="3475c-140">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="3475c-140">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="3475c-141">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="3475c-141">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3475c-142">Note</span><span class="sxs-lookup"><span data-stu-id="3475c-142">Remarks</span></span>

<span data-ttu-id="3475c-143">Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="3475c-143">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="3475c-144">Il provider estende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico. l' `<compiler>` elemento definisce le impostazioni del compilatore e del generatore di codice per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3475c-144">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="3475c-145">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3475c-145">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="3475c-146">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="3475c-146">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="3475c-147">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="3475c-147">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="3475c-148">Gli elementi del compilatore nel file di configurazione dell'applicazione o del Web possono completare o sostituire le impostazioni nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="3475c-148">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="3475c-149">Se è configurata più di un'implementazione del provider per lo stesso nome di linguaggio o per la stessa estensione di file, l'ultima configurazione corrispondente sostituisce tutti i provider configurati in precedenza per il nome o l'estensione di file.</span><span class="sxs-lookup"><span data-stu-id="3475c-149">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="3475c-150">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3475c-150">Configuration File</span></span>

<span data-ttu-id="3475c-151">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3475c-151">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="3475c-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="3475c-152">Example</span></span>

<span data-ttu-id="3475c-153">Nell'esempio seguente viene illustrato un tipico elemento di configurazione del compilatore:</span><span class="sxs-lookup"><span data-stu-id="3475c-153">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3475c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3475c-154">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="3475c-155">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3475c-155">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3475c-156">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="3475c-156">\<compilers> Element</span></span>](compilers-element.md)
- <span data-ttu-id="3475c-157">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="3475c-157">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>
- <span data-ttu-id="3475c-158">[Elemento Compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3475c-158">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
