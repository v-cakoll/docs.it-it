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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155388"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="b8d71-102">\<system.codedom> Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d71-102">\<system.codedom> Element</span></span>
<span data-ttu-id="b8d71-103">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b8d71-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="b8d71-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8d71-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8d71-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b8d71-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b8d71-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b8d71-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8d71-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b8d71-107">Attributes</span></span>  
 <span data-ttu-id="b8d71-108">No.</span><span class="sxs-lookup"><span data-stu-id="b8d71-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8d71-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b8d71-109">Child Elements</span></span>  
  
|<span data-ttu-id="b8d71-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d71-110">Element</span></span>|<span data-ttu-id="b8d71-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8d71-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="b8d71-112">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più [\<compiler>](compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d71-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8d71-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b8d71-113">Parent Elements</span></span>  
  
|<span data-ttu-id="b8d71-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d71-114">Element</span></span>|<span data-ttu-id="b8d71-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8d71-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="b8d71-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8d71-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8d71-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="b8d71-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="b8d71-118">.NET Framework versione 2,0</span><span class="sxs-lookup"><span data-stu-id="b8d71-118">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="b8d71-119">L' [\<system.codedom>](system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio installati in un computer, oltre ai provider predefiniti installati con il .NET Framework, ad esempio <xref:Microsoft.CSharp.CSharpCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="b8d71-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="b8d71-120">L' [\<compilers>](compilers-element.md) elemento contiene zero o più [\<compiler>](compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d71-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="b8d71-121">Ogni [\<compiler>](compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b8d71-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="b8d71-122">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione al file di configurazione del computer (Machine. config) per una nuova <xref:System.CodeDom.Compiler.CodeDomProvider> implementazione.</span><span class="sxs-lookup"><span data-stu-id="b8d71-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b8d71-123">Usare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di codice sia i provider di lingua predefiniti che i provider di linguaggio identificati dalle impostazioni di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="b8d71-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8d71-124">Nelle versioni .NET Framework 1,0 e 1,1, i provider di lingua predefiniti forniti dall'.NET Framework sono identificati nell' [\<compilers>](compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b8d71-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="b8d71-125">In .NET Framework versione 2,0 i provider di lingua predefiniti non sono identificati nell' [\<compilers>](compilers-element.md) elemento, ma possono essere enumerati utilizzando il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b8d71-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="b8d71-126">.NET Framework versioni 1,0 e 1,1</span><span class="sxs-lookup"><span data-stu-id="b8d71-126">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="b8d71-127">L' [\<system.codedom>](system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio in un computer.</span><span class="sxs-lookup"><span data-stu-id="b8d71-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="b8d71-128">L' [\<compilers>](compilers-element.md) elemento contiene zero o più [\<compiler>](compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="b8d71-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="b8d71-129">Ogni [\<compiler>](compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="b8d71-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="b8d71-130">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b8d71-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="b8d71-131">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="b8d71-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b8d71-132">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="b8d71-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b8d71-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b8d71-133">Configuration File</span></span>  
 <span data-ttu-id="b8d71-134">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8d71-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d71-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8d71-135">Example</span></span>  
 <span data-ttu-id="b8d71-136">Nell'esempio seguente viene illustrata una tipica configurazione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b8d71-136">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b8d71-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b8d71-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b8d71-138">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b8d71-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b8d71-139">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="b8d71-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b8d71-140">\<compiler>Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d71-140">\<compiler> Element</span></span>](compiler-element.md)
