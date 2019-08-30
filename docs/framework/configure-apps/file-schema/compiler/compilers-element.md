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
ms.openlocfilehash: 5232c5bd2d4fad8104d156bfa86141ceb7f0dd93
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70167698"
---
# <a name="compilers-element"></a><span data-ttu-id="1fd71-102">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="1fd71-102">\<compilers> Element</span></span>
<span data-ttu-id="1fd71-103">Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="1fd71-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  
  
[<span data-ttu-id="1fd71-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1fd71-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1fd71-105">&nbsp;&nbsp;[ **\<> System. CodeDom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fd71-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="1fd71-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<compilatori >**</span><span class="sxs-lookup"><span data-stu-id="1fd71-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd71-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fd71-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fd71-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1fd71-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1fd71-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1fd71-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fd71-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1fd71-110">Attributes</span></span>  
 <span data-ttu-id="1fd71-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1fd71-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fd71-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1fd71-112">Child Elements</span></span>  
  
|<span data-ttu-id="1fd71-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fd71-113">Element</span></span>|<span data-ttu-id="1fd71-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1fd71-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fd71-115">[\<compiler> Element](compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="1fd71-115">[\<compiler> Element](compiler-element.md)</span></span>|<span data-ttu-id="1fd71-116">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1fd71-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fd71-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1fd71-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1fd71-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fd71-118">Element</span></span>|<span data-ttu-id="1fd71-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fd71-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fd71-120">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="1fd71-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="1fd71-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1fd71-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="1fd71-122">\<Elemento > System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="1fd71-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="1fd71-123">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1fd71-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fd71-124">Note</span><span class="sxs-lookup"><span data-stu-id="1fd71-124">Remarks</span></span>  
 <span data-ttu-id="1fd71-125">Il compilatore > elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio in un computer. [ \<](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fd71-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="1fd71-126">Ogni elemento > del compilatore specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fd71-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="1fd71-127">Il .NET Framework definisce le impostazioni iniziali del compilatore e del provider del linguaggio nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="1fd71-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="1fd71-128">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1fd71-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="1fd71-129">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="1fd71-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1fd71-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1fd71-130">Configuration File</span></span>  
 <span data-ttu-id="1fd71-131">Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1fd71-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fd71-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fd71-132">Example</span></span>  
 <span data-ttu-id="1fd71-133">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="1fd71-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fd71-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fd71-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="1fd71-135">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1fd71-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1fd71-136">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="1fd71-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- <span data-ttu-id="1fd71-137">[\<compiler> Element](compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="1fd71-137">[\<compiler> Element](compiler-element.md)</span></span>
