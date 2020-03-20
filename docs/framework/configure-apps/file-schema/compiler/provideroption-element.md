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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155401"
---
# <a name="provideroption-element"></a><span data-ttu-id="6d620-102">\<Elemento> providerOption</span><span class="sxs-lookup"><span data-stu-id="6d620-102">\<providerOption> Element</span></span>
<span data-ttu-id="6d620-103">Specifica gli attributi di versione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="6d620-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="6d620-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d620-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6d620-105">&nbsp;&nbsp;[**\<>system.codedom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d620-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="6d620-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilatori>**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d620-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="6d620-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del compilatore**](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d620-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="6d620-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>providerOption**</span><span class="sxs-lookup"><span data-stu-id="6d620-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6d620-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d620-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d620-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d620-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6d620-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d620-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d620-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="6d620-112">Attributes</span></span>  
  
|<span data-ttu-id="6d620-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="6d620-113">Attribute</span></span>|<span data-ttu-id="6d620-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d620-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="6d620-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6d620-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="6d620-116">Specifica il nome dell'opzione. ad esempio, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="6d620-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="6d620-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6d620-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="6d620-118">Specifica il valore per l'opzione. ad esempio, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="6d620-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d620-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d620-119">Child Elements</span></span>  
 <span data-ttu-id="6d620-120">No.</span><span class="sxs-lookup"><span data-stu-id="6d620-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d620-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d620-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6d620-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d620-122">Element</span></span>|<span data-ttu-id="6d620-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d620-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d620-124">\<Elemento> configurazione</span><span class="sxs-lookup"><span data-stu-id="6d620-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="6d620-125">Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d620-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="6d620-126">\<system.codedom>elemento</span><span class="sxs-lookup"><span data-stu-id="6d620-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="6d620-127">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="6d620-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="6d620-128">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="6d620-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="6d620-129">Contenitore per gli elementi di configurazione del compilatore; contiene zero `<compiler>` o più elementi.</span><span class="sxs-lookup"><span data-stu-id="6d620-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="6d620-130">\<> del compilatore</span><span class="sxs-lookup"><span data-stu-id="6d620-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="6d620-131">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="6d620-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d620-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6d620-132">Remarks</span></span>  
 <span data-ttu-id="6d620-133">In .NET Framework versione 3.5 i provider di codice CodeDOM (Code Document `<providerOption>` Object Model) possono supportare opzioni specifiche del provider tramite l'elemento .</span><span class="sxs-lookup"><span data-stu-id="6d620-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="6d620-134">.NET Framework 3.5 include assembly .NET Framework 2.0 aggiornati e fornisce assembly della nuova versione 3.5 che contengono nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="6d620-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="6d620-135">I provider di codice di Microsoft C e Visual Basic sono contenuti negli assembly di .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="6d620-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="6d620-136">Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori versione 2.0.By default, the updated code providers generate code for version 2.0 compilers.</span><span class="sxs-lookup"><span data-stu-id="6d620-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="6d620-137">È possibile `<providerOption>` utilizzare l'elemento per modificare la versione del compilatore di destinazione a 3.5.You can use the element to change the target compiler version to 3.5.</span><span class="sxs-lookup"><span data-stu-id="6d620-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="6d620-138">A tale scopo, specificare "CompilerVersion" per `name` l'attributo `value` e "v3.5" per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="6d620-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="6d620-139">È necessario far precedere il numero di versione da una "v" minuscola.</span><span class="sxs-lookup"><span data-stu-id="6d620-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="6d620-140">È possibile rendere globale la `<providerOption>` specifica della versione aggiungendo l'elemento al file Machine.config o Web.config radice di .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="6d620-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="6d620-141">Se si aggiorna la versione predefinita del compilatore a 3.5 nel file Machine.config, è possibile `<providerOption>` ripristinarla a 2.0 in base all'applicazione utilizzando l'elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d620-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="6d620-142">Gli implementatori del provider di codice CodeDOM possono `providerOptions` elaborare <xref:System.Collections.Generic.IDictionary%602>opzioni personalizzate fornendo un costruttore che accetta un parametro di tipo .</span><span class="sxs-lookup"><span data-stu-id="6d620-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d620-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d620-143">Example</span></span>  
 <span data-ttu-id="6d620-144">Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la versione 3.5 del provider di codice C .</span><span class="sxs-lookup"><span data-stu-id="6d620-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d620-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d620-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="6d620-146">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6d620-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6d620-147">\<compilers> Element</span><span class="sxs-lookup"><span data-stu-id="6d620-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="6d620-148">Specifica di nomi di tipo completi</span><span class="sxs-lookup"><span data-stu-id="6d620-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="6d620-149">[Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6d620-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
