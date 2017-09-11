---
title: Attributi comuni (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9adb5cb378701c8d06a3fa28bad44dc857026b5a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="47a17-102">Attributi comuni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a17-102">Common Attributes (Visual Basic)</span></span>
<span data-ttu-id="47a17-103">In questo argomento vengono descritti gli attributi più comunemente utilizzati nei programmi Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47a17-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>  
  
-   [<span data-ttu-id="47a17-104">Attributi globali</span><span class="sxs-lookup"><span data-stu-id="47a17-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="47a17-105">Attributo obsolete</span><span class="sxs-lookup"><span data-stu-id="47a17-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="47a17-106">Attributo condizionale</span><span class="sxs-lookup"><span data-stu-id="47a17-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="47a17-107">Attributi informativi sul chiamante</span><span class="sxs-lookup"><span data-stu-id="47a17-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
-   [<span data-ttu-id="47a17-108">Visual Basic (attributi)</span><span class="sxs-lookup"><span data-stu-id="47a17-108">Visual Basic Attributes</span></span>](#VB)  
  
##  <span data-ttu-id="47a17-109"><a name="Global"></a>Attributi globali</span><span class="sxs-lookup"><span data-stu-id="47a17-109"><a name="Global"></a> Global Attributes</span></span>  
 <span data-ttu-id="47a17-110">Quasi tutti gli attributi vengono applicati agli elementi del linguaggio specifico, ad esempio classi o metodi. Tuttavia, alcuni attributi sono globali, si applicano a un intero assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="47a17-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="47a17-111">Ad esempio, il <xref:System.Reflection.AssemblyVersionAttribute>attributo può essere utilizzato per incorporare le informazioni sulla versione in un assembly, simile al seguente:</xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 <span data-ttu-id="47a17-112">Gli attributi globali vengono visualizzati nel codice sorgente dopo eventuali principale`Imports` istruzioni e prima delle dichiarazioni di tipo, modulo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="47a17-112">Global attributes appear in the source code after any top-level`Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="47a17-113">Gli attributi globali possono essere visualizzati in più file di origine, ma i file devono essere compilati in un singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="47a17-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="47a17-114">Per i progetti di Visual Basic, gli attributi globali vengono in genere inseriti nel file AssemblyInfo. vb (il file viene creato automaticamente quando si crea un progetto in Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="47a17-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>  
  
 <span data-ttu-id="47a17-115">Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="47a17-116">Rientrano nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="47a17-116">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="47a17-117">Attributi di identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="47a17-117">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="47a17-118">Alcuni attributi informativi</span><span class="sxs-lookup"><span data-stu-id="47a17-118">Informational attributes</span></span>  
  
-   <span data-ttu-id="47a17-119">Attributi del manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="47a17-119">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="47a17-120">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="47a17-120">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="47a17-121">Tre attributi (con un nome sicuro, se applicabile) determinano l'identità di un assembly: nome, versione e delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="47a17-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="47a17-122">Questi attributi il nome completo dell'assembly e sono necessari quando si fa riferimento nel codice.</span><span class="sxs-lookup"><span data-stu-id="47a17-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="47a17-123">È possibile impostare versione e le impostazioni cultura utilizzando gli attributi di un assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="47a17-124">Tuttavia, il valore del nome viene impostato dal compilatore, l'IDE di Visual Studio nel [la finestra di dialogo informazioni Assembly](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), o Assembly Linker (Al.exe) quando viene creato l'assembly, in base al file che contiene il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="47a17-125">Il <xref:System.Reflection.AssemblyFlagsAttribute>attributo specifica se è possano la coesistenza di più copie dell'assembly.</xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="47a17-126">Nella tabella seguente vengono illustrati gli attributi di identità.</span><span class="sxs-lookup"><span data-stu-id="47a17-126">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="47a17-127">Attributo</span><span class="sxs-lookup"><span data-stu-id="47a17-127">Attribute</span></span>|<span data-ttu-id="47a17-128">Scopo</span><span class="sxs-lookup"><span data-stu-id="47a17-128">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="47a17-129"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="47a17-129"><xref:System.Reflection.AssemblyName></span></span>|<span data-ttu-id="47a17-130">Viene descritta l'identità di un assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-130">Fully describes the identity of an assembly.</span></span>|  
|<span data-ttu-id="47a17-131"><xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-131"><xref:System.Reflection.AssemblyVersionAttribute></span></span>|<span data-ttu-id="47a17-132">Specifica la versione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-132">Specifies the version of an assembly.</span></span>|  
|<span data-ttu-id="47a17-133"><xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-133"><xref:System.Reflection.AssemblyCultureAttribute></span></span>|<span data-ttu-id="47a17-134">Specifica le impostazioni cultura supportate dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-134">Specifies which culture the assembly supports.</span></span>|  
|<span data-ttu-id="47a17-135"><xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-135"><xref:System.Reflection.AssemblyFlagsAttribute></span></span>|<span data-ttu-id="47a17-136">Specifica se un assembly supporta l'esecuzione side-by-side nello stesso computer, nello stesso processo o nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="47a17-136">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="47a17-137">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="47a17-137">Informational Attributes</span></span>  
 <span data-ttu-id="47a17-138">Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-138">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="47a17-139">Nella tabella seguente vengono illustrati gli attributi informativi definiti nel <xref:System.Reflection?displayProperty=fullName>dello spazio dei nomi.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="47a17-139">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="47a17-140">Attributo</span><span class="sxs-lookup"><span data-stu-id="47a17-140">Attribute</span></span>|<span data-ttu-id="47a17-141">Scopo</span><span class="sxs-lookup"><span data-stu-id="47a17-141">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="47a17-142"><xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-142"><xref:System.Reflection.AssemblyProductAttribute></span></span>|<span data-ttu-id="47a17-143">Definisce un attributo personalizzato che specifica un nome di prodotto per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-143">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-144"><xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-144"><xref:System.Reflection.AssemblyTrademarkAttribute></span></span>|<span data-ttu-id="47a17-145">Definisce un attributo personalizzato che specifica un marchio registrato per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-145">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></span></span>|<span data-ttu-id="47a17-147">Definisce un attributo personalizzato che specifica la versione informativa per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-147">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-148"><xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-148"><xref:System.Reflection.AssemblyCompanyAttribute></span></span>|<span data-ttu-id="47a17-149">Definisce un attributo personalizzato che specifica un nome della società per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-149">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-150"><xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-150"><xref:System.Reflection.AssemblyCopyrightAttribute></span></span>|<span data-ttu-id="47a17-151">Definisce un attributo personalizzato che specifica informazioni sul copyright per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-151">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-152"><xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-152"><xref:System.Reflection.AssemblyFileVersionAttribute></span></span>|<span data-ttu-id="47a17-153">Indica al compilatore di utilizzare un numero di versione specifici per la risorsa di versione del file Win32.</span><span class="sxs-lookup"><span data-stu-id="47a17-153">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<span data-ttu-id="47a17-154"><xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-154"><xref:System.CLSCompliantAttribute></span></span>|<span data-ttu-id="47a17-155">Indica se l'assembly è compatibile con la specifica CLS (Common Language).</span><span class="sxs-lookup"><span data-stu-id="47a17-155">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="47a17-156">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="47a17-156">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="47a17-157">È possibile utilizzare gli attributi del manifesto dell'assembly per fornire informazioni nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-157">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="47a17-158">Sono inclusi titolo, descrizione, alias predefinito e configurazione.</span><span class="sxs-lookup"><span data-stu-id="47a17-158">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="47a17-159">Nella tabella seguente vengono definiscono gli attributi del manifesto dell'assembly nel <xref:System.Reflection?displayProperty=fullName>dello spazio dei nomi.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="47a17-159">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="47a17-160">Attributo</span><span class="sxs-lookup"><span data-stu-id="47a17-160">Attribute</span></span>|<span data-ttu-id="47a17-161">Scopo</span><span class="sxs-lookup"><span data-stu-id="47a17-161">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="47a17-162"><xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-162"><xref:System.Reflection.AssemblyTitleAttribute></span></span>|<span data-ttu-id="47a17-163">Definisce un attributo personalizzato che specifica il titolo dell'assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-163">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-164"><xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-164"><xref:System.Reflection.AssemblyDescriptionAttribute></span></span>|<span data-ttu-id="47a17-165">Definisce un attributo personalizzato che specifica la descrizione dell'assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-165">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-166"><xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-166"><xref:System.Reflection.AssemblyConfigurationAttribute></span></span>|<span data-ttu-id="47a17-167">Definisce un attributo personalizzato che specifica la configurazione dell'assembly (ad esempio finale o di debug) per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="47a17-167">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<span data-ttu-id="47a17-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></span></span>|<span data-ttu-id="47a17-169">Definisce un alias predefinito descrittivo per un manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="47a17-169">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <span data-ttu-id="47a17-170"><a name="Obsolete"></a>Attributo obsolete</span><span class="sxs-lookup"><span data-stu-id="47a17-170"><a name="Obsolete"></a> Obsolete Attribute</span></span>  
 <span data-ttu-id="47a17-171">Il `Obsolete` attributo contrassegna un'entità che non è più consigliato per l'utilizzo del programma.</span><span class="sxs-lookup"><span data-stu-id="47a17-171">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="47a17-172">Ciascun utilizzo di un'entità contrassegnata successivamente genererà un avviso o errore, a seconda della configurazione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="47a17-172">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="47a17-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47a17-173">For example:</span></span>  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="47a17-174">In questo esempio il `Obsolete` attributo viene applicato alla classe `A` e al metodo `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="47a17-174">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="47a17-175">Poiché il secondo argomento del costruttore dell'attributo applicato a `B.OldMethod` è impostato su `true`, questo metodo genererà un errore del compilatore, mentre l'utilizzo di classe `A` produrrà semplicemente un avviso.</span><span class="sxs-lookup"><span data-stu-id="47a17-175">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="47a17-176">La chiamata `B.NewMethod`, tuttavia, non produce alcun avviso o errore.</span><span class="sxs-lookup"><span data-stu-id="47a17-176">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="47a17-177">La stringa fornita come primo argomento al costruttore dell'attributo verrà visualizzata come parte dell'avviso o errore.</span><span class="sxs-lookup"><span data-stu-id="47a17-177">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="47a17-178">Ad esempio, se utilizzato con le definizioni precedenti, il codice seguente genera un errore e due avvisi:</span><span class="sxs-lookup"><span data-stu-id="47a17-178">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 <span data-ttu-id="47a17-179">Due avvisi per la classe `A` generati: uno per la dichiarazione del riferimento della classe e uno per il costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="47a17-179">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="47a17-180">Il `Obsolete` attributo può essere utilizzato senza argomenti, ma inclusi una spiegazione del motivo per cui l'elemento è obsoleto e gli elementi da utilizzare in alternativa è consigliata.</span><span class="sxs-lookup"><span data-stu-id="47a17-180">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="47a17-181">Il `Obsolete` è un attributo a utilizzo singolo e può essere applicato a qualsiasi entità che supporta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="47a17-181">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="47a17-182">`Obsolete`è un alias per <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-182">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <span data-ttu-id="47a17-183"><a name="Conditional"></a>Attributo condizionale</span><span class="sxs-lookup"><span data-stu-id="47a17-183"><a name="Conditional"></a> Conditional Attribute</span></span>  
 <span data-ttu-id="47a17-184">Il `Conditional` attributo rende l'esecuzione di un metodo dipendente da un identificatore di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="47a17-184">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="47a17-185">Il `Conditional` attributo è un alias per <xref:System.Diagnostics.ConditionalAttribute>e può essere applicato a un metodo o una classe di attributo.</xref:System.Diagnostics.ConditionalAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-185">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="47a17-186">In questo esempio, `Conditional` viene applicato a un metodo per attivare o disattivare la visualizzazione delle informazioni di diagnostica specifici del programma:</span><span class="sxs-lookup"><span data-stu-id="47a17-186">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="47a17-187">Se il `TRACE_ON` identificatore non è definito, non verrà visualizzato alcun output di traccia.</span><span class="sxs-lookup"><span data-stu-id="47a17-187">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="47a17-188">Il `Conditional` attributo viene spesso utilizzato con il `DEBUG` identificatore per abilitare la traccia e funzioni di registrazione per le compilazioni di debug ma non in versioni finali, come segue:</span><span class="sxs-lookup"><span data-stu-id="47a17-188">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 <span data-ttu-id="47a17-189">Quando viene chiamato un metodo contrassegnato come condizionali, la presenza o l'assenza del simbolo di pre-elaborazione specificato determina se la chiamata è incluso o omesso.</span><span class="sxs-lookup"><span data-stu-id="47a17-189">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="47a17-190">Se il simbolo è definito, la chiamata è inclusa; in caso contrario, viene omessa.</span><span class="sxs-lookup"><span data-stu-id="47a17-190">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="47a17-191">Utilizzando `Conditional` è un'alternativa più semplice, più elegante e meno soggetto a errori rispetto all'inclusione di metodi all'interno di `#if…#endif` blocchi, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="47a17-191">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 <span data-ttu-id="47a17-192">Un metodo condizionale deve essere un metodo in una dichiarazione di classe o uno struct e non deve avere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="47a17-192">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="47a17-193">Utilizzo di più identificatori</span><span class="sxs-lookup"><span data-stu-id="47a17-193">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="47a17-194">Se un metodo ha più `Conditional` gli attributi, una chiamata al metodo è inclusa se almeno uno dei simboli condizionali sia definito (in altre parole, i simboli sono logicamente collegati tra loro mediante l'operatore OR).</span><span class="sxs-lookup"><span data-stu-id="47a17-194">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="47a17-195">In questo esempio, la presenza di `A` o `B` determinerà una chiamata al metodo:</span><span class="sxs-lookup"><span data-stu-id="47a17-195">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 <span data-ttu-id="47a17-196">Per ottenere l'effetto di collegamento logico di simboli tramite l'operatore AND, è possibile definire metodi condizionali seriali.</span><span class="sxs-lookup"><span data-stu-id="47a17-196">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="47a17-197">Ad esempio, il secondo metodo riportato di seguito verrà eseguito solo se entrambi `A` e `B` vengono definiti:</span><span class="sxs-lookup"><span data-stu-id="47a17-197">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="47a17-198">Con le classi di attributi condizionali</span><span class="sxs-lookup"><span data-stu-id="47a17-198">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="47a17-199">Il `Conditional` attributo può anche essere applicato a una definizione di classe attribute.</span><span class="sxs-lookup"><span data-stu-id="47a17-199">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="47a17-200">In questo esempio, l'attributo personalizzato `Documentation` aggiungerà le informazioni solo per i metadati se DEBUG è definito.</span><span class="sxs-lookup"><span data-stu-id="47a17-200">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <span data-ttu-id="47a17-201"><a name="CallerInfo"></a>Attributi informativi sul chiamante</span><span class="sxs-lookup"><span data-stu-id="47a17-201"><a name="CallerInfo"></a> Caller Info Attributes</span></span>  
 <span data-ttu-id="47a17-202">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="47a17-202">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="47a17-203">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del membro del chiamante.</span><span class="sxs-lookup"><span data-stu-id="47a17-203">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="47a17-204">Per ottenere informazioni sul chiamante, utilizzare gli attributi applicati ai parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="47a17-204">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="47a17-205">Ciascun parametro facoltativo specifica un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="47a17-205">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="47a17-206">Nella tabella seguente vengono elencati gli attributi di informazioni sul chiamante definiti nel <xref:System.Runtime.CompilerServices?displayProperty=fullName>dello spazio dei nomi:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="47a17-206">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="47a17-207">Attributo</span><span class="sxs-lookup"><span data-stu-id="47a17-207">Attribute</span></span>|<span data-ttu-id="47a17-208">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47a17-208">Description</span></span>|<span data-ttu-id="47a17-209">Tipo</span><span class="sxs-lookup"><span data-stu-id="47a17-209">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="47a17-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="47a17-211">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="47a17-211">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="47a17-212">Si tratta del percorso in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="47a17-212">This is the path at compile time.</span></span>|`String`|  
|<span data-ttu-id="47a17-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="47a17-214">Numero di riga nel file di origine da cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="47a17-214">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="47a17-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="47a17-216">Nome di metodo o proprietà del chiamante.</span><span class="sxs-lookup"><span data-stu-id="47a17-216">Method name or property name of the caller.</span></span> <span data-ttu-id="47a17-217">Per ulteriori informazioni, vedere [informazioni sul chiamante (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="47a17-217">For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="47a17-218">Per ulteriori informazioni sugli attributi di informazioni sul chiamante, vedere [informazioni sul chiamante (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="47a17-218">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
##  <span data-ttu-id="47a17-219"><a name="VB"></a>Visual Basic (attributi)</span><span class="sxs-lookup"><span data-stu-id="47a17-219"><a name="VB"></a> Visual Basic Attributes</span></span>  
 <span data-ttu-id="47a17-220">Nella tabella seguente vengono elencati gli attributi specifici di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47a17-220">The following table lists the attributes that are specific to Visual Basic.</span></span>  
  
|<span data-ttu-id="47a17-221">Attributo</span><span class="sxs-lookup"><span data-stu-id="47a17-221">Attribute</span></span>|<span data-ttu-id="47a17-222">Scopo</span><span class="sxs-lookup"><span data-stu-id="47a17-222">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="47a17-223"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-223"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="47a17-224">Indica al compilatore che la classe deve essere esposto come un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="47a17-224">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|  
|<span data-ttu-id="47a17-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="47a17-226">Consente ai membri del modulo a cui accedere utilizzando solo la qualifica necessaria per il modulo.</span><span class="sxs-lookup"><span data-stu-id="47a17-226">Allows module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="47a17-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="47a17-228">Specifica la dimensione di una stringa a lunghezza fissa in una struttura da utilizzare con file di input e output funzioni.</span><span class="sxs-lookup"><span data-stu-id="47a17-228">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|  
|<span data-ttu-id="47a17-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="47a17-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="47a17-230">Specifica la dimensione di una matrice fissa in una struttura da utilizzare con file di input e output funzioni.</span><span class="sxs-lookup"><span data-stu-id="47a17-230">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|  
  
### <a name="comclassattribute"></a><span data-ttu-id="47a17-231">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="47a17-231">COMClassAttribute</span></span>  
 <span data-ttu-id="47a17-232">Utilizzare `COMClassAttribute` per semplificare il processo di creazione di componenti COM da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47a17-232">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="47a17-233">Gli oggetti COM sono notevolmente diversi dagli assembly .NET Framework e senza `COMClassAttribute`, è necessario seguire una serie di passaggi per generare un oggetto COM da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47a17-233">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="47a17-234">Per le classi contrassegnate con `COMClassAttribute`, il compilatore esegue automaticamente molti di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="47a17-234">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>  
  
### <a name="hidemodulenameattribute"></a><span data-ttu-id="47a17-235">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="47a17-235">HideModuleNameAttribute</span></span>  
 <span data-ttu-id="47a17-236">Utilizzare `HideModuleNameAttribute` per consentire l'accesso utilizzando solo la qualifica necessaria per il modulo ai membri del modulo.</span><span class="sxs-lookup"><span data-stu-id="47a17-236">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>  
  
### <a name="vbfixedstringattribute"></a><span data-ttu-id="47a17-237">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="47a17-237">VBFixedStringAttribute</span></span>  
 <span data-ttu-id="47a17-238">Utilizzare `VBFixedStringAttribute` per forzare Visual Basic per creare una stringa a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="47a17-238">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="47a17-239">Le stringhe sono di lunghezza variabile per impostazione predefinita, e questo attributo è utile quando si archiviano stringhe nei file.</span><span class="sxs-lookup"><span data-stu-id="47a17-239">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="47a17-240">Il codice seguente illustra questo processo:</span><span class="sxs-lookup"><span data-stu-id="47a17-240">The following code demonstrates this:</span></span>  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a><span data-ttu-id="47a17-241">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="47a17-241">VBFixedArrayAttribute</span></span>  
 <span data-ttu-id="47a17-242">Utilizzare `VBFixedArrayAttribute` per dichiarare matrici di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="47a17-242">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="47a17-243">Le stringhe di Visual Basic, le matrici sono di lunghezza variabile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="47a17-243">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="47a17-244">Questo attributo è utile durante la serializzazione o la scrittura di dati nei file.</span><span class="sxs-lookup"><span data-stu-id="47a17-244">This attribute is useful when serializing or writing data to files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a17-245">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47a17-245">See Also</span></span>  
 <span data-ttu-id="47a17-246"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="47a17-246"><xref:System.Reflection></span></span>   
 <span data-ttu-id="47a17-247"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="47a17-247"><xref:System.Attribute></span></span>   
<span data-ttu-id="47a17-248"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="47a17-248"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="47a17-249"> [Attributi](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="47a17-249"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="47a17-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="47a17-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="47a17-251"> [Accesso agli attributi tramite Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="47a17-251"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
