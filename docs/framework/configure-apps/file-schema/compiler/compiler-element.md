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
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088049"
---
# <a name="compiler-element"></a><span data-ttu-id="5e618-102">\<compiler> Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-102">\<compiler> Element</span></span>

<span data-ttu-id="5e618-103">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e618-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

## <a name="syntax"></a><span data-ttu-id="5e618-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e618-104">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5e618-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5e618-105">Attributes and Elements</span></span>

<span data-ttu-id="5e618-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5e618-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5e618-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5e618-107">Attributes</span></span>

|<span data-ttu-id="5e618-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5e618-108">Attribute</span></span>|<span data-ttu-id="5e618-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e618-109">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="5e618-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e618-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5e618-111">Specifica argomenti aggiuntivi specifici del compilatore per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="5e618-111">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="5e618-112">I valori per l' `compilerOptions` attributo sono in genere elencati in un argomento delle opzioni del compilatore per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="5e618-112">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="5e618-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e618-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e618-114">Fornisce un elenco delimitato da punti e virgola delle estensioni di file utilizzate dai file di origine per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e618-114">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="5e618-115">come ad esempio ".cs".</span><span class="sxs-lookup"><span data-stu-id="5e618-115">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="5e618-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e618-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e618-117">Fornisce un elenco delimitato da punti e virgola di nomi di lingua supportati dal provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e618-117">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="5e618-118">come ad esempio "C#;cs;csharp".</span><span class="sxs-lookup"><span data-stu-id="5e618-118">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="5e618-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e618-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="5e618-120">Specifica il nome del tipo del provider del linguaggio, incluso il nome dell'assembly che contiene l'implementazione del provider.</span><span class="sxs-lookup"><span data-stu-id="5e618-120">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="5e618-121">Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="5e618-121">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="5e618-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e618-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5e618-123">Specifica il livello di avviso predefinito del compilatore. determina il livello al quale il provider del linguaggio considera gli avvisi di compilazione come errori.</span><span class="sxs-lookup"><span data-stu-id="5e618-123">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5e618-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5e618-124">Child Elements</span></span>

|<span data-ttu-id="5e618-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-125">Element</span></span>|<span data-ttu-id="5e618-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e618-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e618-127">\<providerOption>Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-127">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="5e618-128">Specifica gli attributi della versione del compilatore per un provider di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e618-128">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5e618-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5e618-129">Parent Elements</span></span>

|<span data-ttu-id="5e618-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-130">Element</span></span>|<span data-ttu-id="5e618-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e618-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e618-132">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-132">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="5e618-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e618-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="5e618-134">\<system.codedom>Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-134">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="5e618-135">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e618-135">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="5e618-136">\<compilers>Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-136">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="5e618-137">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="5e618-137">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5e618-138">Commenti</span><span class="sxs-lookup"><span data-stu-id="5e618-138">Remarks</span></span>

<span data-ttu-id="5e618-139">Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="5e618-139">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="5e618-140">Il provider estende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico. l' `<compiler>` elemento definisce le impostazioni del compilatore e del generatore di codice per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="5e618-140">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="5e618-141">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5e618-141">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="5e618-142">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="5e618-142">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="5e618-143">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="5e618-143">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="5e618-144">Gli elementi del compilatore nel file di configurazione dell'applicazione o del Web possono completare o sostituire le impostazioni nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="5e618-144">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="5e618-145">Se è configurata più di un'implementazione del provider per lo stesso nome di linguaggio o per la stessa estensione di file, l'ultima configurazione corrispondente sostituisce tutti i provider configurati in precedenza per il nome o l'estensione di file.</span><span class="sxs-lookup"><span data-stu-id="5e618-145">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="5e618-146">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5e618-146">Configuration File</span></span>

<span data-ttu-id="5e618-147">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e618-147">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="5e618-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e618-148">Example</span></span>

<span data-ttu-id="5e618-149">Nell'esempio seguente viene illustrato un tipico elemento di configurazione del compilatore:</span><span class="sxs-lookup"><span data-stu-id="5e618-149">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5e618-150">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5e618-150">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="5e618-151">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="5e618-151">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5e618-152">\<compilers>Elemento</span><span class="sxs-lookup"><span data-stu-id="5e618-152">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="5e618-153">Specifica di nomi di tipo completi</span><span class="sxs-lookup"><span data-stu-id="5e618-153">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="5e618-154">[Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5e618-154">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
