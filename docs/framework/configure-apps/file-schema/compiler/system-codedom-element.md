---
title: Elemento <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155388"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="b61ba-102">\<system.codedom>elemento</span><span class="sxs-lookup"><span data-stu-id="b61ba-102">\<system.codedom> Element</span></span>
<span data-ttu-id="b61ba-103">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b61ba-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="b61ba-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="b61ba-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b61ba-105">&nbsp;&nbsp;**\<>system.codedom**</span><span class="sxs-lookup"><span data-stu-id="b61ba-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61ba-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b61ba-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b61ba-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b61ba-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b61ba-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b61ba-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b61ba-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="b61ba-109">Attributes</span></span>  
 <span data-ttu-id="b61ba-110">No.</span><span class="sxs-lookup"><span data-stu-id="b61ba-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b61ba-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b61ba-111">Child Elements</span></span>  
  
|<span data-ttu-id="b61ba-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="b61ba-112">Element</span></span>|<span data-ttu-id="b61ba-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b61ba-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b61ba-114">\<compilatori></span><span class="sxs-lookup"><span data-stu-id="b61ba-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="b61ba-115">Contenitore per gli elementi di configurazione del compilatore; contiene zero [ \<](compiler-element.md) o più elementi>del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b61ba-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b61ba-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b61ba-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b61ba-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b61ba-117">Element</span></span>|<span data-ttu-id="b61ba-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b61ba-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b61ba-119">\<>di configurazione</span><span class="sxs-lookup"><span data-stu-id="b61ba-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="b61ba-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b61ba-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b61ba-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b61ba-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="b61ba-122">.NET Framework versione 2.0</span><span class="sxs-lookup"><span data-stu-id="b61ba-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="b61ba-123">L'elemento [ \<system.codedom>](system-codedom-element.md) contiene le impostazioni di configurazione del compilatore per i provider del linguaggio <xref:Microsoft.CSharp.CSharpCodeProvider> installati <xref:Microsoft.VisualBasic.VBCodeProvider>in un computer oltre ai provider predefiniti installati con .NET Framework, ad esempio e .</span><span class="sxs-lookup"><span data-stu-id="b61ba-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="b61ba-124">L'elemento [ \<>compilatori](compilers-element.md) contiene zero o più [ \<elementi>compilatore.](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="b61ba-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="b61ba-125">Ogni elemento [ \<>del compilatore](compiler-element.md) specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b61ba-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="b61ba-126">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni <xref:System.CodeDom.Compiler.CodeDomProvider> di configurazione al file di configurazione del computer (Machine.config) per una nuova implementazione.</span><span class="sxs-lookup"><span data-stu-id="b61ba-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b61ba-127">Utilizzare <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> il metodo per enumerare a livello di codice sia i provider di linguaggio predefiniti che i provider di linguaggio identificati dalle impostazioni di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="b61ba-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b61ba-128">In .NET Framework versioni 1.0 e 1.1 i provider di linguaggi predefiniti forniti da .NET Framework vengono identificati nell'elemento [ \<>compilatori.](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="b61ba-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="b61ba-129">In .NET Framework versione 2.0 i provider di linguaggi predefiniti non sono identificati nell'elemento <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> [ \<>compilatori,](compilers-element.md) ma possono essere enumerati utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="b61ba-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="b61ba-130">.NET Framework versioni 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="b61ba-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="b61ba-131">L'elemento [ \<system.codedom>](system-codedom-element.md) contiene le impostazioni di configurazione del compilatore per i provider di linguaggiinun computer.</span><span class="sxs-lookup"><span data-stu-id="b61ba-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="b61ba-132">L'elemento [ \<>compilatori](compilers-element.md) contiene zero o più [ \<elementi>compilatore.](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="b61ba-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="b61ba-133">Ogni elemento [ \<>del compilatore](compiler-element.md) specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b61ba-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="b61ba-134">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b61ba-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="b61ba-135">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="b61ba-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b61ba-136">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="b61ba-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b61ba-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b61ba-137">Configuration File</span></span>  
 <span data-ttu-id="b61ba-138">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b61ba-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b61ba-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="b61ba-139">Example</span></span>  
 <span data-ttu-id="b61ba-140">Nell'esempio seguente viene illustrata una configurazione tipica del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b61ba-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b61ba-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b61ba-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b61ba-142">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b61ba-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b61ba-143">Schema delle impostazioni del compilatore e del provider di linguaggioCompiler and Language Provider Settings Schema</span><span class="sxs-lookup"><span data-stu-id="b61ba-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b61ba-144">\<> del compilatore</span><span class="sxs-lookup"><span data-stu-id="b61ba-144">\<compiler> Element</span></span>](compiler-element.md)
