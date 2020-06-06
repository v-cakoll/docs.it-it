---
title: <providerOption> Elemento
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155401"
---
# <a name="provideroption-element"></a><span data-ttu-id="1982e-102">\<providerOption> Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-102">\<providerOption> Element</span></span>
<span data-ttu-id="1982e-103">Specifica gli attributi della versione del compilatore per un provider di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1982e-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="1982e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1982e-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1982e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1982e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1982e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1982e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1982e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1982e-107">Attributes</span></span>  
  
|<span data-ttu-id="1982e-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="1982e-108">Attribute</span></span>|<span data-ttu-id="1982e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1982e-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="1982e-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1982e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="1982e-111">Specifica il nome dell'opzione. ad esempio, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="1982e-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="1982e-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1982e-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="1982e-113">Specifica il valore per l'opzione. ad esempio, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="1982e-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1982e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1982e-114">Child Elements</span></span>  
 <span data-ttu-id="1982e-115">No.</span><span class="sxs-lookup"><span data-stu-id="1982e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1982e-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1982e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1982e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-117">Element</span></span>|<span data-ttu-id="1982e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1982e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1982e-119">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="1982e-120">Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1982e-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="1982e-121">\<system.codedom>Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="1982e-122">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1982e-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="1982e-123">\<compilers>Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="1982e-124">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="1982e-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="1982e-125">\<compiler>Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="1982e-126">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1982e-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1982e-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="1982e-127">Remarks</span></span>  
 <span data-ttu-id="1982e-128">In .NET Framework versione 3,5 i provider di codice Code Document Object Model (CodeDOM) possono supportare opzioni specifiche del provider tramite l' `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="1982e-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="1982e-129">Il .NET Framework 3,5 include gli assembly .NET Framework 2,0 aggiornati e fornisce nuovi assembly della versione 3,5 che contengono nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="1982e-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="1982e-130">I provider di codice Microsoft C# e Visual Basic sono contenuti in .NET Framework assembly 2,0, ma sono stati aggiornati per supportare i compilatori della versione 3,5.</span><span class="sxs-lookup"><span data-stu-id="1982e-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="1982e-131">Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori della versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="1982e-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="1982e-132">È possibile usare l' `<providerOption>` elemento per modificare la versione del compilatore di destinazione in 3,5.</span><span class="sxs-lookup"><span data-stu-id="1982e-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="1982e-133">A tale scopo, specificare "CompilerVersion" per l' `name` attributo e "v 3.5" per l' `value` attributo.</span><span class="sxs-lookup"><span data-stu-id="1982e-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="1982e-134">Il numero di versione deve essere preceduto da un minuscolo "v".</span><span class="sxs-lookup"><span data-stu-id="1982e-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="1982e-135">È possibile rendere globale la specifica della versione aggiungendo l' `<providerOption>` elemento al file di .NET Framework 2,0 Machine. config o al file Web. config radice.</span><span class="sxs-lookup"><span data-stu-id="1982e-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="1982e-136">Se si aggiorna la versione del compilatore predefinita a 3,5 nel file Machine. config, è possibile reimpostarla su 2,0 per ogni singola applicazione usando l' `<providerOption>` elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1982e-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="1982e-137">Gli implementatori del provider di codice CodeDOM possono elaborare opzioni personalizzate fornendo un costruttore che accetta un `providerOptions` parametro di tipo <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="1982e-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1982e-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="1982e-138">Example</span></span>  
 <span data-ttu-id="1982e-139">Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la versione 3,5 del provider di codice C#.</span><span class="sxs-lookup"><span data-stu-id="1982e-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1982e-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1982e-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="1982e-141">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1982e-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1982e-142">\<compilers>Elemento</span><span class="sxs-lookup"><span data-stu-id="1982e-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="1982e-143">Specifica di nomi di tipo completi</span><span class="sxs-lookup"><span data-stu-id="1982e-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="1982e-144">[Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1982e-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
