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
ms.openlocfilehash: 0f47255bb4073007a847e4a8b85ccfd34100582b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101614"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="4f4fc-102">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="4f4fc-102">\<system.codedom> Element</span></span>
<span data-ttu-id="4f4fc-103">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="4f4fc-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="4f4fc-104">\<configuration> Element</span></span>  
<span data-ttu-id="4f4fc-105">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="4f4fc-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f4fc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f4fc-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f4fc-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f4fc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4f4fc-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f4fc-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f4fc-109">Attributes</span></span>  
 <span data-ttu-id="4f4fc-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f4fc-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f4fc-111">Child Elements</span></span>  
  
|<span data-ttu-id="4f4fc-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f4fc-112">Element</span></span>|<span data-ttu-id="4f4fc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f4fc-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f4fc-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="4f4fc-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="4f4fc-115">Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="4f4fc-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f4fc-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f4fc-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4f4fc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f4fc-117">Element</span></span>|<span data-ttu-id="4f4fc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f4fc-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f4fc-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f4fc-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="4f4fc-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f4fc-121">Note</span><span class="sxs-lookup"><span data-stu-id="4f4fc-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="4f4fc-122">.NET framework versione 2.0</span><span class="sxs-lookup"><span data-stu-id="4f4fc-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="4f4fc-123">Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi installati in un computer oltre i provider predefiniti che vengono installati con .NET Framework, ad esempio il <xref:Microsoft.CSharp.CSharpCodeProvider> e il <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="4f4fc-124">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="4f4fc-125">Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="4f4fc-126">Gli sviluppatori e i produttori di compilatori possono aggiungere le impostazioni di configurazione al file di configurazione del computer (Machine. config) per un nuovo <xref:System.CodeDom.Compiler.CodeDomProvider> implementazione.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="4f4fc-127">Usare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di codice sia il provider del linguaggio predefiniti e i provider di linguaggi identificati dalle impostazioni di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f4fc-128">In .NET Framework versioni 1.0 e 1.1, la lingua predefinita provider forniti da .NET Framework sono identificati i [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="4f4fc-129">In .NET Framework versione 2.0, il provider di linguaggi predefiniti non sono identificate nel [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento, ma possono essere enumerati utilizzando il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="4f4fc-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="4f4fc-130">.NET framework versioni 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="4f4fc-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="4f4fc-131">Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi in un computer.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="4f4fc-132">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="4f4fc-133">Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="4f4fc-134">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4f4fc-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4f4fc-135">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="4f4fc-136">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4f4fc-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4f4fc-137">Configuration File</span></span>  
 <span data-ttu-id="4f4fc-138">Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4fc-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f4fc-139">Example</span></span>  
 <span data-ttu-id="4f4fc-140">L'esempio seguente illustra una configurazione tipica del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4f4fc-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f4fc-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f4fc-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="4f4fc-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4f4fc-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4f4fc-143">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="4f4fc-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- <span data-ttu-id="4f4fc-144">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="4f4fc-144">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>
