---
title: '&lt;System. CodeDom&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5939fa31a2f87348922d4586e3e7b7b52066fb09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744226"
---
# <a name="ltsystemcodedomgt-element"></a><span data-ttu-id="ed0c4-102">&lt;System. CodeDom&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="ed0c4-102">&lt;system.codedom&gt; Element</span></span>
<span data-ttu-id="ed0c4-103">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="ed0c4-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="ed0c4-104">\<configuration> Element</span></span>  
<span data-ttu-id="ed0c4-105">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="ed0c4-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0c4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed0c4-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed0c4-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ed0c4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ed0c4-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed0c4-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="ed0c4-109">Attributes</span></span>  
 <span data-ttu-id="ed0c4-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed0c4-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ed0c4-111">Child Elements</span></span>  
  
|<span data-ttu-id="ed0c4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed0c4-112">Element</span></span>|<span data-ttu-id="ed0c4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed0c4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed0c4-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="ed0c4-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="ed0c4-115">Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="ed0c4-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed0c4-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ed0c4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ed0c4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed0c4-117">Element</span></span>|<span data-ttu-id="ed0c4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed0c4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed0c4-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ed0c4-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ed0c4-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed0c4-121">Note</span><span class="sxs-lookup"><span data-stu-id="ed0c4-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="ed0c4-122">.NET framework versione 2.0</span><span class="sxs-lookup"><span data-stu-id="ed0c4-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="ed0c4-123">Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per provider di linguaggi installati in un computer oltre a provider predefiniti installati con .NET Framework, ad esempio il <xref:Microsoft.CSharp.CSharpCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="ed0c4-124">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="ed0c4-125">Ogni [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="ed0c4-126">Gli sviluppatori e i fornitori di compilatori possono aggiungere le impostazioni di configurazione al file di configurazione del computer (Machine. config) per un nuovo <xref:System.CodeDom.Compiler.CodeDomProvider> implementazione.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="ed0c4-127">Utilizzare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di programmazione sia i provider di linguaggi predefiniti e i provider di linguaggio identificati le impostazioni di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed0c4-128">In .NET Framework versioni 1.0 e 1.1, la lingua predefinita provider forniti da .NET Framework vengono identificati il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="ed0c4-129">In .NET Framework versione 2.0, il provider di linguaggi predefiniti non sono identificate nel [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento, ma possono essere enumerati utilizzando il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="ed0c4-130">Versioni di .NET framework 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="ed0c4-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="ed0c4-131">Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per il provider di linguaggi in un computer.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="ed0c4-132">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="ed0c4-133">Ogni [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="ed0c4-134">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ed0c4-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="ed0c4-135">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="ed0c4-136">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ed0c4-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ed0c4-137">Configuration File</span></span>  
 <span data-ttu-id="ed0c4-138">Questo elemento può essere usato nel file di configurazione del computer e i file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed0c4-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed0c4-139">Example</span></span>  
 <span data-ttu-id="ed0c4-140">Nell'esempio seguente viene illustrata una configurazione tipica del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ed0c4-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed0c4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0c4-141">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="ed0c4-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ed0c4-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ed0c4-143">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="ed0c4-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 <span data-ttu-id="ed0c4-144">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="ed0c4-144">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>
