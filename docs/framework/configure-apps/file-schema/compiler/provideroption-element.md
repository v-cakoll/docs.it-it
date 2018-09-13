---
title: '&lt;providerOption&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 75cc2003a88cc7be467b9062c37b6b5d9eb82f53
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706028"
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="9da07-102">&lt;providerOption&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="9da07-103">Specifica gli attributi di versione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9da07-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="9da07-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="9da07-104">\<configuration Element></span></span>  
<span data-ttu-id="9da07-105">\<Elemento System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="9da07-105">\<system.codedom Element></span></span>  
<span data-ttu-id="9da07-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="9da07-106">\<compilers Element></span></span>  
<span data-ttu-id="9da07-107">\<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-107">\<compiler> Element</span></span>  
<span data-ttu-id="9da07-108">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da07-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9da07-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9da07-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9da07-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9da07-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9da07-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9da07-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9da07-112">Attributes</span></span>  
  
|<span data-ttu-id="9da07-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9da07-113">Attribute</span></span>|<span data-ttu-id="9da07-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9da07-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9da07-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9da07-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9da07-116">Specifica il nome dell'opzione; ad esempio, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="9da07-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="9da07-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9da07-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="9da07-118">Specifica il valore per l'opzione. ad esempio, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="9da07-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9da07-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9da07-119">Child Elements</span></span>  
 <span data-ttu-id="9da07-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9da07-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9da07-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9da07-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9da07-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-122">Element</span></span>|<span data-ttu-id="9da07-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9da07-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9da07-124">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="9da07-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9da07-125">Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9da07-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9da07-126">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="9da07-127">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="9da07-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="9da07-128">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="9da07-129">Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="9da07-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|<span data-ttu-id="9da07-130">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="9da07-130">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>|<span data-ttu-id="9da07-131">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9da07-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9da07-132">Note</span><span class="sxs-lookup"><span data-stu-id="9da07-132">Remarks</span></span>  
 <span data-ttu-id="9da07-133">In .NET Framework versione 3.5, i provider di codice Code Document Object Model (CodeDOM) possono supportare opzioni specifiche del provider usando la `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="9da07-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="9da07-134">.NET Framework 3.5 include gli assembly di .NET Framework 2.0 aggiornati e fornisce nuovi assembly della versione 3.5 che contengono nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="9da07-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="9da07-135">I provider di codice Microsoft c# e Visual Basic sono contenuti negli assembly di .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori di versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="9da07-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="9da07-136">Per impostazione predefinita, i provider di codice aggiornato generano codice per i compilatori di versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="9da07-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="9da07-137">È possibile usare il `<providerOption>` elemento per modificare la versione del compilatore di destinazione a 3.5.</span><span class="sxs-lookup"><span data-stu-id="9da07-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="9da07-138">A questo scopo, specificare "CompilerVersion" per il `name` attributo e "v3.5" per il `value` attributo.</span><span class="sxs-lookup"><span data-stu-id="9da07-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="9da07-139">È necessario anteporre il numero di versione con lettere minuscole "v".</span><span class="sxs-lookup"><span data-stu-id="9da07-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="9da07-140">È possibile rendere la specifica della versione globale mediante l'aggiunta di `<providerOption>` elemento per il file Machine. config di .NET Framework 2.0 o un file Web. config radice.</span><span class="sxs-lookup"><span data-stu-id="9da07-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="9da07-141">Se si aggiorna la versione del compilatore predefinito 3.5 nel file Machine. config, è possibile modificarlo al 2.0 su una base all'applicazione tramite il `<providerOption>` elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9da07-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="9da07-142">I responsabili dell'implementazione del provider di codice codeDOM può elaborare le opzioni personalizzate, fornendo un costruttore che accetta un `providerOptions` parametru typu <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="9da07-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9da07-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="9da07-143">Example</span></span>  
 <span data-ttu-id="9da07-144">Nell'esempio seguente viene illustrato come specificare la versione 3.5 del provider di codice c# da usare.</span><span class="sxs-lookup"><span data-stu-id="9da07-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9da07-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9da07-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="9da07-146">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="9da07-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9da07-147">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="9da07-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 <span data-ttu-id="9da07-148">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="9da07-148">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>  
 [<span data-ttu-id="9da07-149">Elemento Compiler per compilers per compilation (Schema delle impostazioni ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="9da07-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
