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
ms.openlocfilehash: fa3410cc2c8812c59528676bfad6cd7e887c5f73
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746397"
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="d6585-102">&lt;providerOption&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="d6585-103">Specifica gli attributi di versione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="d6585-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="d6585-104">\<Elemento di configurazione ></span><span class="sxs-lookup"><span data-stu-id="d6585-104">\<configuration Element></span></span>  
<span data-ttu-id="d6585-105">\<Elemento System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="d6585-105">\<system.codedom Element></span></span>  
<span data-ttu-id="d6585-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="d6585-106">\<compilers Element></span></span>  
<span data-ttu-id="d6585-107">\<compilatore > elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-107">\<compiler> Element</span></span>  
<span data-ttu-id="d6585-108">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6585-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6585-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6585-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6585-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6585-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6585-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6585-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6585-112">Attributes</span></span>  
  
|<span data-ttu-id="d6585-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d6585-113">Attribute</span></span>|<span data-ttu-id="d6585-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6585-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d6585-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6585-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="d6585-116">Specifica il nome dell'opzione. ad esempio, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="d6585-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="d6585-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6585-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="d6585-118">Specifica il valore per l'opzione. ad esempio, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="d6585-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6585-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6585-119">Child Elements</span></span>  
 <span data-ttu-id="d6585-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d6585-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6585-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6585-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d6585-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-122">Element</span></span>|<span data-ttu-id="d6585-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6585-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6585-124">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="d6585-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="d6585-125">Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6585-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="d6585-126">\<System. CodeDom > elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="d6585-127">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="d6585-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="d6585-128">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="d6585-129">Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.</span><span class="sxs-lookup"><span data-stu-id="d6585-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|<span data-ttu-id="d6585-130">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)</span><span class="sxs-lookup"><span data-stu-id="d6585-130">[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)</span></span>|<span data-ttu-id="d6585-131">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="d6585-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6585-132">Note</span><span class="sxs-lookup"><span data-stu-id="d6585-132">Remarks</span></span>  
 <span data-ttu-id="d6585-133">In .NET Framework versione 3.5, il provider di codice Code Document Object Model (CodeDOM) può supportare opzioni specifiche del provider utilizzando il `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d6585-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="d6585-134">.NET Framework 3.5 include gli assembly di .NET Framework 2.0 aggiornati e fornisce nuovi assembly versione 3.5 contenenti nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="d6585-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="d6585-135">I provider di codice Microsoft c# e Visual Basic sono contenuti in assembly .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="d6585-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="d6585-136">Per impostazione predefinita, i provider di codice aggiornato generano codice per i compilatori versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="d6585-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="d6585-137">È possibile utilizzare il `<providerOption>` elemento per modificare la versione del compilatore di destinazione in 3.5.</span><span class="sxs-lookup"><span data-stu-id="d6585-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="d6585-138">A tale scopo, specificare "CompilerVersion" per il `name` attributo e "v 3.5" per il `value` attributo.</span><span class="sxs-lookup"><span data-stu-id="d6585-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="d6585-139">È necessario anteporre il numero di versione con una lettera minuscola "v".</span><span class="sxs-lookup"><span data-stu-id="d6585-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="d6585-140">È possibile rendere la specifica della versione globale aggiungendo il `<providerOption>` elemento per il file Machine. config di .NET Framework 2.0 o un file Web. config radice.</span><span class="sxs-lookup"><span data-stu-id="d6585-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="d6585-141">Se si aggiorna la versione del compilatore predefinita in 3.5 nel file Machine. config, è possibile ripristinare 2.0 per ogni applicazione utilizzando il `<providerOption>` elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6585-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="d6585-142">Gli implementatori di provider di codice codeDOM possono elaborare opzioni personalizzate fornendo un costruttore che accetta un `providerOptions` parametro di tipo <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="d6585-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6585-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6585-143">Example</span></span>  
 <span data-ttu-id="d6585-144">Nell'esempio seguente viene illustrato come specificare la versione 3.5 del provider di codice c# deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d6585-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6585-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6585-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="d6585-146">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d6585-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d6585-147">\<i compilatori > elemento</span><span class="sxs-lookup"><span data-stu-id="d6585-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 <span data-ttu-id="d6585-148">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)</span><span class="sxs-lookup"><span data-stu-id="d6585-148">[Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)</span></span>  
 [<span data-ttu-id="d6585-149">compilatore elemento per i compilatori per compilation (Schema delle impostazioni ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="d6585-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
