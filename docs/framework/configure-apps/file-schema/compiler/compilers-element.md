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
ms.openlocfilehash: 09b1efe321c39402c9280eda0e9def9112462470
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155414"
---
# <a name="compilers-element"></a><span data-ttu-id="337f7-102">\<compilers> Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-102">\<compilers> Element</span></span>
<span data-ttu-id="337f7-103">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più [\<compiler>](compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="337f7-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="337f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="337f7-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="337f7-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="337f7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="337f7-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="337f7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="337f7-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="337f7-107">Attributes</span></span>  
 <span data-ttu-id="337f7-108">No.</span><span class="sxs-lookup"><span data-stu-id="337f7-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="337f7-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="337f7-109">Child Elements</span></span>  
  
|<span data-ttu-id="337f7-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-110">Element</span></span>|<span data-ttu-id="337f7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="337f7-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="337f7-112">\<compiler>Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="337f7-113">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="337f7-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="337f7-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="337f7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="337f7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-115">Element</span></span>|<span data-ttu-id="337f7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="337f7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="337f7-117">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="337f7-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="337f7-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="337f7-119">\<system.codedom>Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="337f7-120">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="337f7-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="337f7-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="337f7-121">Remarks</span></span>  
 <span data-ttu-id="337f7-122">L' [\<compilers>](compilers-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio in un computer.</span><span class="sxs-lookup"><span data-stu-id="337f7-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="337f7-123">Ogni [\<compiler>](compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="337f7-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="337f7-124">Il .NET Framework definisce le impostazioni iniziali del compilatore e del provider del linguaggio nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="337f7-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="337f7-125">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="337f7-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="337f7-126">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="337f7-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="337f7-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="337f7-127">Configuration File</span></span>  
 <span data-ttu-id="337f7-128">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337f7-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="337f7-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="337f7-129">Example</span></span>  
 <span data-ttu-id="337f7-130">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="337f7-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="337f7-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="337f7-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="337f7-132">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="337f7-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="337f7-133">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="337f7-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="337f7-134">\<compiler>Elemento</span><span class="sxs-lookup"><span data-stu-id="337f7-134">\<compiler> Element</span></span>](compiler-element.md)
