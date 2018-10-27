---
title: '&lt;i compilatori&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a73c3e8f554d2c78252ca763a620d05c5b494884
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50041544"
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="6f36c-102">&lt;i compilatori&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="6f36c-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="6f36c-103">Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="6f36c-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="6f36c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6f36c-104">\<configuration></span></span>  
<span data-ttu-id="6f36c-105">\<System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="6f36c-105">\<system.codedom></span></span>  
<span data-ttu-id="6f36c-106">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="6f36c-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f36c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f36c-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f36c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6f36c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6f36c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6f36c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f36c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6f36c-110">Attributes</span></span>  
 <span data-ttu-id="6f36c-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6f36c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6f36c-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6f36c-112">Child Elements</span></span>  
  
|<span data-ttu-id="6f36c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f36c-113">Element</span></span>|<span data-ttu-id="6f36c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f36c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f36c-115">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="6f36c-115">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>|<span data-ttu-id="6f36c-116">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="6f36c-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f36c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6f36c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6f36c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f36c-118">Element</span></span>|<span data-ttu-id="6f36c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f36c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f36c-120">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="6f36c-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6f36c-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f36c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="6f36c-122">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="6f36c-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="6f36c-123">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="6f36c-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f36c-124">Note</span><span class="sxs-lookup"><span data-stu-id="6f36c-124">Remarks</span></span>  
 <span data-ttu-id="6f36c-125">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi in un computer.</span><span class="sxs-lookup"><span data-stu-id="6f36c-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="6f36c-126">Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="6f36c-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="6f36c-127">.NET Framework definisce le impostazioni di provider di linguaggio e del compilatore iniziali nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="6f36c-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="6f36c-128">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f36c-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="6f36c-129">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="6f36c-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6f36c-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f36c-130">Configuration File</span></span>  
 <span data-ttu-id="6f36c-131">Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f36c-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f36c-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f36c-132">Example</span></span>  
 <span data-ttu-id="6f36c-133">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="6f36c-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f36c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f36c-134">See Also</span></span>  
- <xref:System.CodeDom.Compiler.CompilerInfo>  
- <xref:System.CodeDom.Compiler.CodeDomProvider>  
- [<span data-ttu-id="6f36c-135">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f36c-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="6f36c-136">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="6f36c-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
- <span data-ttu-id="6f36c-137">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="6f36c-137">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>
