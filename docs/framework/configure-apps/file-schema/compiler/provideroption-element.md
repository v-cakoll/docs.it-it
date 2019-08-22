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
ms.openlocfilehash: 37f4d8c5eeacd82f8fc37179c478d026ca25f459
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664309"
---
# <a name="provideroption-element"></a><span data-ttu-id="359c9-102">\<Elemento > providerOption</span><span class="sxs-lookup"><span data-stu-id="359c9-102">\<providerOption> Element</span></span>
<span data-ttu-id="359c9-103">Specifica gli attributi della versione del compilatore per un provider di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="359c9-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="359c9-104">\<> elemento di configurazione</span><span class="sxs-lookup"><span data-stu-id="359c9-104">\<configuration Element></span></span>  
<span data-ttu-id="359c9-105">\<Elemento System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="359c9-105">\<system.codedom Element></span></span>  
<span data-ttu-id="359c9-106">\<> elemento compilatori</span><span class="sxs-lookup"><span data-stu-id="359c9-106">\<compilers Element></span></span>  
<span data-ttu-id="359c9-107">\<Elemento > del compilatore</span><span class="sxs-lookup"><span data-stu-id="359c9-107">\<compiler> Element</span></span>  
<span data-ttu-id="359c9-108">\<Elemento > providerOption</span><span class="sxs-lookup"><span data-stu-id="359c9-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359c9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="359c9-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="359c9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="359c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="359c9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="359c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="359c9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="359c9-112">Attributes</span></span>  
  
|<span data-ttu-id="359c9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="359c9-113">Attribute</span></span>|<span data-ttu-id="359c9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="359c9-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="359c9-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="359c9-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="359c9-116">Specifica il nome dell'opzione. ad esempio, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="359c9-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="359c9-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="359c9-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="359c9-118">Specifica il valore per l'opzione. ad esempio, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="359c9-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="359c9-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="359c9-119">Child Elements</span></span>  
 <span data-ttu-id="359c9-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="359c9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="359c9-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="359c9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="359c9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="359c9-122">Element</span></span>|<span data-ttu-id="359c9-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="359c9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="359c9-124">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="359c9-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="359c9-125">Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="359c9-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="359c9-126">\<Elemento > System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="359c9-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="359c9-127">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="359c9-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="359c9-128">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="359c9-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="359c9-129">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="359c9-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|<span data-ttu-id="359c9-130">[\<compiler> Element](compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="359c9-130">[\<compiler> Element](compiler-element.md)</span></span>|<span data-ttu-id="359c9-131">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="359c9-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="359c9-132">Note</span><span class="sxs-lookup"><span data-stu-id="359c9-132">Remarks</span></span>  
 <span data-ttu-id="359c9-133">In .NET Framework versione 3,5 i provider di codice Code Document Object Model (CodeDom) possono supportare opzioni specifiche del provider tramite l' `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="359c9-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="359c9-134">Il .NET Framework 3,5 include gli assembly .NET Framework 2,0 aggiornati e fornisce nuovi assembly della versione 3,5 che contengono nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="359c9-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="359c9-135">I provider C# di codice Microsoft e Visual Basic sono contenuti in .NET Framework assembly 2,0, ma sono stati aggiornati per supportare i compilatori della versione 3,5.</span><span class="sxs-lookup"><span data-stu-id="359c9-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="359c9-136">Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori della versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="359c9-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="359c9-137">È possibile usare l' `<providerOption>` elemento per modificare la versione del compilatore di destinazione in 3,5.</span><span class="sxs-lookup"><span data-stu-id="359c9-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="359c9-138">A tale scopo, specificare "CompilerVersion" per l' `name` attributo e "v 3.5" per l' `value` attributo.</span><span class="sxs-lookup"><span data-stu-id="359c9-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="359c9-139">Il numero di versione deve essere preceduto da un minuscolo "v".</span><span class="sxs-lookup"><span data-stu-id="359c9-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="359c9-140">È possibile rendere globale la specifica della versione aggiungendo l' `<providerOption>` elemento al file di .NET Framework 2,0 Machine. config o al file Web. config radice.</span><span class="sxs-lookup"><span data-stu-id="359c9-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="359c9-141">Se si aggiorna la versione del compilatore predefinita a 3,5 nel file Machine. config, è possibile reimpostarla su 2,0 per ogni singola applicazione usando l' `<providerOption>` elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="359c9-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="359c9-142">Gli implementatori del provider di codice CodeDOM possono elaborare opzioni personalizzate fornendo un costruttore che `providerOptions` accetta un parametro <xref:System.Collections.Generic.IDictionary%602>di tipo.</span><span class="sxs-lookup"><span data-stu-id="359c9-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="359c9-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="359c9-143">Example</span></span>  
 <span data-ttu-id="359c9-144">Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la C# versione 3,5 del provider di codice.</span><span class="sxs-lookup"><span data-stu-id="359c9-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="359c9-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="359c9-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="359c9-146">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="359c9-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="359c9-147">\<compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="359c9-147">\<compilers> Element</span></span>](compilers-element.md)
- <span data-ttu-id="359c9-148">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="359c9-148">[Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>
- <span data-ttu-id="359c9-149">[Elemento Compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="359c9-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
