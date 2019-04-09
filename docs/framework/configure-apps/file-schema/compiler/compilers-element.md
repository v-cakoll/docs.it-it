---
title: <compilers> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 744ef0d9bc58e6a0152dce53c40c24eb5283dc0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130520"
---
# <a name="compilers-element"></a><span data-ttu-id="c6c3a-102">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-102">\<compilers> Element</span></span>
<span data-ttu-id="c6c3a-103">Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="c6c3a-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="c6c3a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c6c3a-104">\<configuration></span></span>  
<span data-ttu-id="c6c3a-105">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="c6c3a-105">\<system.codedom></span></span>  
<span data-ttu-id="c6c3a-106">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c3a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6c3a-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6c3a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c6c3a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c6c3a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6c3a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="c6c3a-110">Attributes</span></span>  
 <span data-ttu-id="c6c3a-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6c3a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c6c3a-112">Child Elements</span></span>  
  
|<span data-ttu-id="c6c3a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-113">Element</span></span>|<span data-ttu-id="c6c3a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6c3a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6c3a-115">\<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="c6c3a-116">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6c3a-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c6c3a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c6c3a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-118">Element</span></span>|<span data-ttu-id="c6c3a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6c3a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6c3a-120">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="c6c3a-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="c6c3a-122">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="c6c3a-123">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c3a-124">Note</span><span class="sxs-lookup"><span data-stu-id="c6c3a-124">Remarks</span></span>  
 <span data-ttu-id="c6c3a-125">Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi in un computer.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="c6c3a-126">Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="c6c3a-127">.NET Framework definisce le impostazioni di provider di linguaggio e del compilatore iniziali nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="c6c3a-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="c6c3a-128">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="c6c3a-129">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c6c3a-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6c3a-130">Configuration File</span></span>  
 <span data-ttu-id="c6c3a-131">Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c3a-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6c3a-132">Example</span></span>  
 <span data-ttu-id="c6c3a-133">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6c3a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6c3a-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="c6c3a-135">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6c3a-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c6c3a-136">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="c6c3a-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="c6c3a-137">\<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="c6c3a-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
