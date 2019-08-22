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
ms.openlocfilehash: 80eea3373e2f4b7e45ebeb31dd6552ea02c109e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659724"
---
# <a name="compiler-element"></a><span data-ttu-id="87790-102">\<Elemento > del compilatore</span><span class="sxs-lookup"><span data-stu-id="87790-102">\<compiler> Element</span></span>

<span data-ttu-id="87790-103">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87790-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="87790-104">\<elemento Configuration > \<elemento System. CodeDom > \<compilers elemento \<> elemento > del compilatore</span><span class="sxs-lookup"><span data-stu-id="87790-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="87790-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87790-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87790-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="87790-106">Attributes and Elements</span></span>

<span data-ttu-id="87790-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="87790-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="87790-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="87790-108">Attributes</span></span>

|<span data-ttu-id="87790-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="87790-109">Attribute</span></span>|<span data-ttu-id="87790-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87790-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="87790-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="87790-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87790-112">Specifica argomenti aggiuntivi specifici del compilatore per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="87790-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="87790-113">I valori per l' `compilerOptions` attributo sono in genere elencati in un argomento delle opzioni del compilatore per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="87790-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="87790-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87790-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="87790-115">Fornisce un elenco delimitato da punti e virgola delle estensioni di file utilizzate dai file di origine per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87790-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="87790-116">Ad esempio, ". cs".</span><span class="sxs-lookup"><span data-stu-id="87790-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="87790-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87790-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="87790-118">Fornisce un elenco delimitato da punti e virgola di nomi di lingua supportati dal provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87790-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="87790-119">Ad esempio, "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="87790-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="87790-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87790-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="87790-121">Specifica il nome del tipo del provider del linguaggio, incluso il nome dell'assembly che contiene l'implementazione del provider.</span><span class="sxs-lookup"><span data-stu-id="87790-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="87790-122">Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="87790-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="87790-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="87790-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87790-124">Specifica il livello di avviso predefinito del compilatore. determina il livello al quale il provider del linguaggio considera gli avvisi di compilazione come errori.</span><span class="sxs-lookup"><span data-stu-id="87790-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="87790-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="87790-125">Child Elements</span></span>

|<span data-ttu-id="87790-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="87790-126">Element</span></span>|<span data-ttu-id="87790-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87790-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87790-128">\<Elemento > providerOption</span><span class="sxs-lookup"><span data-stu-id="87790-128">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="87790-129">Specifica gli attributi della versione del compilatore per un provider di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87790-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="87790-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="87790-130">Parent Elements</span></span>

|<span data-ttu-id="87790-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="87790-131">Element</span></span>|<span data-ttu-id="87790-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87790-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87790-133">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="87790-133">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="87790-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87790-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="87790-135">\<Elemento > System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="87790-135">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="87790-136">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="87790-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="87790-137">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="87790-137">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="87790-138">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="87790-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="87790-139">Note</span><span class="sxs-lookup"><span data-stu-id="87790-139">Remarks</span></span>

<span data-ttu-id="87790-140">Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="87790-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="87790-141">Il provider estende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico. l' `<compiler>` elemento definisce le impostazioni del compilatore e del generatore di codice per il provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87790-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="87790-142">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="87790-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="87790-143">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="87790-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="87790-144">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="87790-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="87790-145">Gli elementi del compilatore nel file di configurazione dell'applicazione o del Web possono completare o sostituire le impostazioni nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="87790-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="87790-146">Se è configurata più di un'implementazione del provider per lo stesso nome di linguaggio o per la stessa estensione di file, l'ultima configurazione corrispondente sostituisce tutti i provider configurati in precedenza per il nome o l'estensione di file.</span><span class="sxs-lookup"><span data-stu-id="87790-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="87790-147">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="87790-147">Configuration File</span></span>

<span data-ttu-id="87790-148">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87790-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="87790-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="87790-149">Example</span></span>

<span data-ttu-id="87790-150">Nell'esempio seguente viene illustrato un tipico elemento di configurazione del compilatore:</span><span class="sxs-lookup"><span data-stu-id="87790-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87790-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87790-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="87790-152">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="87790-152">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="87790-153">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="87790-153">\<compilers> Element</span></span>](compilers-element.md)
- <span data-ttu-id="87790-154">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="87790-154">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>
- <span data-ttu-id="87790-155">[Elemento Compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="87790-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
