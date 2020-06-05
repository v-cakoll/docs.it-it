---
title: Attributi comuni
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400719"
---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="1aafb-102">Attributi comuni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aafb-102">Common Attributes (Visual Basic)</span></span>

<span data-ttu-id="1aafb-103">In questo argomento vengono descritti gli attributi usati più di frequente nei programmi Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1aafb-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>

- [<span data-ttu-id="1aafb-104">Attributi globali</span><span class="sxs-lookup"><span data-stu-id="1aafb-104">Global Attributes</span></span>](#Global)

- [<span data-ttu-id="1aafb-105">Attributo obsolete</span><span class="sxs-lookup"><span data-stu-id="1aafb-105">Obsolete Attribute</span></span>](#Obsolete)

- [<span data-ttu-id="1aafb-106">Attributo condizionale</span><span class="sxs-lookup"><span data-stu-id="1aafb-106">Conditional Attribute</span></span>](#Conditional)

- [<span data-ttu-id="1aafb-107">Attributi delle informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="1aafb-107">Caller Info Attributes</span></span>](#CallerInfo)

- [<span data-ttu-id="1aafb-108">Attributi di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1aafb-108">Visual Basic Attributes</span></span>](#VB)

## <a name="global-attributes"></a><a name="Global"></a><span data-ttu-id="1aafb-109">Attributi globali</span><span class="sxs-lookup"><span data-stu-id="1aafb-109">Global Attributes</span></span>

<span data-ttu-id="1aafb-110">La maggior parte degli attributi viene applicata a elementi specifici del linguaggio quali classi o metodi. Alcuni attributi sono invece globali e vengono applicati a un intero assembly o a un intero modulo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="1aafb-111">Ad esempio, l'attributo <xref:System.Reflection.AssemblyVersionAttribute> può essere usato per incorporare informazioni sulla versione in un assembly, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1aafb-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

<span data-ttu-id="1aafb-112">Gli attributi globali vengono visualizzati nel codice sorgente dopo qualsiasi istruzione di primo livello `Imports` e prima delle dichiarazioni di tipo, modulo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1aafb-112">Global attributes appear in the source code after any top-level `Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="1aafb-113">Gli attributi globali possono apparire in più file di origine, ma i file devono essere compilati in un'unica operazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1aafb-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="1aafb-114">Per i progetti Visual Basic, gli attributi globali vengono in genere inseriti nel file AssemblyInfo. vb. il file viene creato automaticamente quando si crea un progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1aafb-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>

<span data-ttu-id="1aafb-115">Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="1aafb-116">Sono suddivisi nelle seguenti categorie:</span><span class="sxs-lookup"><span data-stu-id="1aafb-116">They fall into the following categories:</span></span>

- <span data-ttu-id="1aafb-117">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="1aafb-117">Assembly identity attributes</span></span>

- <span data-ttu-id="1aafb-118">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="1aafb-118">Informational attributes</span></span>

- <span data-ttu-id="1aafb-119">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="1aafb-119">Assembly manifest attributes</span></span>

### <a name="assembly-identity-attributes"></a><span data-ttu-id="1aafb-120">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="1aafb-120">Assembly Identity Attributes</span></span>

<span data-ttu-id="1aafb-121">Tre attributi (con un nome sicuro, se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="1aafb-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="1aafb-122">Questi attributi formano il nome completo dell'assembly e sono necessari per creare riferimenti all'assembly nel codice.</span><span class="sxs-lookup"><span data-stu-id="1aafb-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="1aafb-123">È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="1aafb-124">Tuttavia il valore del nome viene impostato alla creazione dell'assembly dal compilatore (l'IDE di Visual Studio nella [finestra di dialogo informazioni Assembly](/visualstudio/ide/reference/assembly-information-dialog-box) oppure Assembly Linker, Al.exe), in base al file che contiene il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="1aafb-125">L'attributo <xref:System.Reflection.AssemblyFlagsAttribute> specifica se è supportata la coesistenza di più copie dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="1aafb-126">La tabella seguente visualizza gli attributi relativi all'identità.</span><span class="sxs-lookup"><span data-stu-id="1aafb-126">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="1aafb-127">Attributo</span><span class="sxs-lookup"><span data-stu-id="1aafb-127">Attribute</span></span>|<span data-ttu-id="1aafb-128">Scopo</span><span class="sxs-lookup"><span data-stu-id="1aafb-128">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="1aafb-129">Descrive in modo completo l'identità di un assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-129">Fully describes the identity of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="1aafb-130">Specifica la versione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-130">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="1aafb-131">Specifica le impostazioni cultura supportate dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-131">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="1aafb-132">Specifica se un assembly supporta l'esecuzione side-by-side nello stesso computer, nello stesso processo o nello stesso dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1aafb-132">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

### <a name="informational-attributes"></a><span data-ttu-id="1aafb-133">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="1aafb-133">Informational Attributes</span></span>

<span data-ttu-id="1aafb-134">Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-134">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="1aafb-135">La tabella seguente mostra gli attributi informativi definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1aafb-135">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="1aafb-136">Attributo</span><span class="sxs-lookup"><span data-stu-id="1aafb-136">Attribute</span></span>|<span data-ttu-id="1aafb-137">Scopo</span><span class="sxs-lookup"><span data-stu-id="1aafb-137">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="1aafb-138">Definisce un attributo personalizzato che specifica un nome prodotto per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-138">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="1aafb-139">Definisce un attributo personalizzato che specifica un marchio registrato per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-139">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="1aafb-140">Definisce un attributo personalizzato che specifica una versione informativa per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-140">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="1aafb-141">Definisce un attributo personalizzato che specifica un nome società per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-141">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="1aafb-142">Definisce un attributo personalizzato che specifica un copyright per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-142">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="1aafb-143">Indica al compilatore di usare un numero di versione specifico per la risorsa della versione del file Win32.</span><span class="sxs-lookup"><span data-stu-id="1aafb-143">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="1aafb-144">Indica se l'assembly è conforme a CLS (Common Language Specification).</span><span class="sxs-lookup"><span data-stu-id="1aafb-144">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

### <a name="assembly-manifest-attributes"></a><span data-ttu-id="1aafb-145">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="1aafb-145">Assembly Manifest Attributes</span></span>

<span data-ttu-id="1aafb-146">È possibile usare gli attributi relativi al manifesto dell'assembly per includere informazioni nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-146">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="1aafb-147">Queste informazioni includono il titolo, la descrizione, l'alias predefinito e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="1aafb-147">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="1aafb-148">La tabella seguente visualizza gli attributi del manifesto dell'assembly definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1aafb-148">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="1aafb-149">Attributo</span><span class="sxs-lookup"><span data-stu-id="1aafb-149">Attribute</span></span>|<span data-ttu-id="1aafb-150">Scopo</span><span class="sxs-lookup"><span data-stu-id="1aafb-150">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="1aafb-151">Definisce un attributo personalizzato che specifica un titolo assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-151">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="1aafb-152">Definisce un attributo personalizzato che specifica una descrizione assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-152">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="1aafb-153">Definisce un attributo personalizzato che specifica una configurazione assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-153">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="1aafb-154">Definisce un alias predefinito descrittivo per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1aafb-154">Defines a friendly default alias for an assembly manifest</span></span>|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a><span data-ttu-id="1aafb-155">Attributo obsolete</span><span class="sxs-lookup"><span data-stu-id="1aafb-155">Obsolete Attribute</span></span>

<span data-ttu-id="1aafb-156">L'attributo `Obsolete` contrassegna un'entità del programma il cui uso non è più consigliato.</span><span class="sxs-lookup"><span data-stu-id="1aafb-156">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="1aafb-157">Ogni uso di un'entità contrassegnata con Obsolete genererà in seguito un avviso o errore, a seconda della configurazione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-157">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="1aafb-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1aafb-158">For example:</span></span>

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

<span data-ttu-id="1aafb-159">Nel seguente esempio l'attributo `Obsolete` viene applicato alla classe `A` e al metodo `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="1aafb-159">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="1aafb-160">Poiché il secondo argomento del costruttore dell'attributo applicato a `B.OldMethod` è impostato su `true` questo metodo genererà un errore del compilatore, mentre l'uso della classe `A` produrrà semplicemente un avviso.</span><span class="sxs-lookup"><span data-stu-id="1aafb-160">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="1aafb-161">Tuttavia la chiamata di `B.NewMethod` non produrrà né un avviso né un errore.</span><span class="sxs-lookup"><span data-stu-id="1aafb-161">Calling `B.NewMethod`, however, produces no warning or error.</span></span>

<span data-ttu-id="1aafb-162">La stringa specificata come primo argomento al costruttore dell'attributo viene inclusa nell'avviso o nell'errore visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1aafb-162">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="1aafb-163">Ad esempio, se viene usato con le definizioni precedenti, il codice che segue genera due avvisi e un errore:</span><span class="sxs-lookup"><span data-stu-id="1aafb-163">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

<span data-ttu-id="1aafb-164">Vengono generati due avvisi per la classe `A`: uno per la dichiarazione del riferimento alla classe e uno per il costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="1aafb-164">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>

<span data-ttu-id="1aafb-165">L'attributo `Obsolete` può essere usato senza argomenti, ma è consigliabile includere la spiegazione del motivo per cui l'elemento è obsoleto e l'indicazione degli elementi di codice da usare come alternativa.</span><span class="sxs-lookup"><span data-stu-id="1aafb-165">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>

<span data-ttu-id="1aafb-166">`Obsolete` è un attributo monouso e può essere applicato a qualsiasi entità che supporta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="1aafb-166">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="1aafb-167">`Obsolete` è un alias per <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1aafb-167">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

## <a name="conditional-attribute"></a><a name="Conditional"></a> <span data-ttu-id="1aafb-168">Attributo Conditional</span><span class="sxs-lookup"><span data-stu-id="1aafb-168">Conditional Attribute</span></span>

<span data-ttu-id="1aafb-169">L'attributo `Conditional` rende l'esecuzione di un metodo dipendente da un identificatore di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1aafb-169">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="1aafb-170">L'attributo `Conditional` è un alias per <xref:System.Diagnostics.ConditionalAttribute> e può essere applicato a un metodo o a una classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="1aafb-170">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="1aafb-171">In questo esempio, `Conditional` viene applicato a un metodo per attivare o disattivare la visualizzazione di informazioni di diagnostica specifiche del programma:</span><span class="sxs-lookup"><span data-stu-id="1aafb-171">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

```vb
#Const TRACE_ON = True
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

<span data-ttu-id="1aafb-172">Se l'identificatore `TRACE_ON` non è definito, non viene visualizzato nessun output di traccia.</span><span class="sxs-lookup"><span data-stu-id="1aafb-172">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>

<span data-ttu-id="1aafb-173">L'attributo `Conditional` viene usato spesso con l'identificatore `DEBUG` per abilitare funzioni di traccia e registrazione nelle compilazioni di debug ma non nelle build di rilascio, come segue:</span><span class="sxs-lookup"><span data-stu-id="1aafb-173">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

<span data-ttu-id="1aafb-174">Quando viene chiamato un metodo contrassegnato come condizionale, la presenza o l'assenza del simbolo di pre-elaborazione specificato determina se la chiamata viene inclusa o omessa.</span><span class="sxs-lookup"><span data-stu-id="1aafb-174">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="1aafb-175">Se il simbolo è definito la chiamata viene inclusa, in caso contrario viene omessa.</span><span class="sxs-lookup"><span data-stu-id="1aafb-175">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="1aafb-176">L'uso di `Conditional` rappresenta un'alternativa più efficiente, elegante e meno soggetta a errori rispetto all'inclusione di metodi nei blocchi `#if…#endif` come segue:</span><span class="sxs-lookup"><span data-stu-id="1aafb-176">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

<span data-ttu-id="1aafb-177">Un metodo condizionale deve essere un metodo in una dichiarazione di classe o struct e non deve avere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="1aafb-177">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>

### <a name="using-multiple-identifiers"></a><span data-ttu-id="1aafb-178">Usare più identificatori</span><span class="sxs-lookup"><span data-stu-id="1aafb-178">Using Multiple Identifiers</span></span>

<span data-ttu-id="1aafb-179">Se un metodo ha più attributi `Conditional`, una chiamata al metodo è inclusa se è definito almeno uno dei simboli condizionali (in altre parole, se i simboli sono collegati tra loro a livello logico mediante l'operatore OR).</span><span class="sxs-lookup"><span data-stu-id="1aafb-179">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="1aafb-180">In questo esempio la presenza di `A` o `B` determina una chiamata al metodo:</span><span class="sxs-lookup"><span data-stu-id="1aafb-180">In this example, the presence of either `A` or `B` will result in a method call:</span></span>

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

<span data-ttu-id="1aafb-181">Per ottenere il collegamento logico di simboli tramite l'operatore AND è possibile definire metodi condizionali seriali.</span><span class="sxs-lookup"><span data-stu-id="1aafb-181">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="1aafb-182">Ad esempio, il secondo metodo riportato di seguito viene eseguito solo se sono definiti sia `A` sia `B`:</span><span class="sxs-lookup"><span data-stu-id="1aafb-182">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>

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

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="1aafb-183">Usare Conditional con le classi di attributi</span><span class="sxs-lookup"><span data-stu-id="1aafb-183">Using Conditional with Attribute Classes</span></span>

<span data-ttu-id="1aafb-184">L'attributo `Conditional` può essere applicato anche a una definizione di classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="1aafb-184">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="1aafb-185">In questo esempio l'attributo personalizzato `Documentation` aggiunge le informazioni ai metadati solo se è definito l'elemento DEBUG.</span><span class="sxs-lookup"><span data-stu-id="1aafb-185">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>

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

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a><span data-ttu-id="1aafb-186">Attributi delle informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="1aafb-186">Caller Info Attributes</span></span>

<span data-ttu-id="1aafb-187">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-187">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="1aafb-188">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1aafb-188">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>

<span data-ttu-id="1aafb-189">È possibile ottenere informazioni sul chiamante usando gli attributi applicati ai parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1aafb-189">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="1aafb-190">Ogni parametro facoltativo specifica un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1aafb-190">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="1aafb-191">Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1aafb-191">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="1aafb-192">Attributo</span><span class="sxs-lookup"><span data-stu-id="1aafb-192">Attribute</span></span>|<span data-ttu-id="1aafb-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1aafb-193">Description</span></span>|<span data-ttu-id="1aafb-194">Type</span><span class="sxs-lookup"><span data-stu-id="1aafb-194">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="1aafb-195">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="1aafb-195">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="1aafb-196">È il percorso al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="1aafb-196">This is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="1aafb-197">Numero di riga nel file di origine da cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-197">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="1aafb-198">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="1aafb-198">Method name or property name of the caller.</span></span> <span data-ttu-id="1aafb-199">Per ulteriori informazioni, vedere [informazioni sul chiamante (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="1aafb-199">For more information, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>|`String`|

<span data-ttu-id="1aafb-200">Per ulteriori informazioni sugli attributi delle informazioni sul chiamante, vedere [informazioni sul chiamante (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="1aafb-200">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>

## <a name="visual-basic-attributes"></a><a name="VB"></a><span data-ttu-id="1aafb-201">Attributi di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1aafb-201">Visual Basic Attributes</span></span>

<span data-ttu-id="1aafb-202">Nella tabella seguente sono elencati gli attributi specifici per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1aafb-202">The following table lists the attributes that are specific to Visual Basic.</span></span>

|<span data-ttu-id="1aafb-203">Attributo</span><span class="sxs-lookup"><span data-stu-id="1aafb-203">Attribute</span></span>|<span data-ttu-id="1aafb-204">Scopo</span><span class="sxs-lookup"><span data-stu-id="1aafb-204">Purpose</span></span>|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|<span data-ttu-id="1aafb-205">Indica al compilatore che la classe deve essere esposta come oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="1aafb-205">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|<span data-ttu-id="1aafb-206">Consente l'accesso ai membri del modulo usando solo la qualifica necessaria per il modulo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-206">Allows module members to be accessed using only the qualification needed for the module.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|<span data-ttu-id="1aafb-207">Specifica la dimensione di una stringa a lunghezza fissa in una struttura da utilizzare con le funzioni di input e output di file.</span><span class="sxs-lookup"><span data-stu-id="1aafb-207">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|<span data-ttu-id="1aafb-208">Specifica la dimensione di una matrice fissa in una struttura da utilizzare con le funzioni di input e output di file.</span><span class="sxs-lookup"><span data-stu-id="1aafb-208">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|

### <a name="comclassattribute"></a><span data-ttu-id="1aafb-209">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="1aafb-209">COMClassAttribute</span></span>

<span data-ttu-id="1aafb-210">Usare `COMClassAttribute` per semplificare il processo di creazione di componenti com da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1aafb-210">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="1aafb-211">Gli oggetti COM sono molto diversi dagli assembly .NET Framework e senza `COMClassAttribute` , è necessario seguire una serie di passaggi per generare un oggetto com da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1aafb-211">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="1aafb-212">Per le classi contrassegnate con `COMClassAttribute` , il compilatore esegue automaticamente molti di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="1aafb-212">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>

### <a name="hidemodulenameattribute"></a><span data-ttu-id="1aafb-213">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="1aafb-213">HideModuleNameAttribute</span></span>

<span data-ttu-id="1aafb-214">Usare `HideModuleNameAttribute` per consentire l'accesso ai membri del modulo usando solo la qualifica necessaria per il modulo.</span><span class="sxs-lookup"><span data-stu-id="1aafb-214">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>

### <a name="vbfixedstringattribute"></a><span data-ttu-id="1aafb-215">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="1aafb-215">VBFixedStringAttribute</span></span>

<span data-ttu-id="1aafb-216">Usare `VBFixedStringAttribute` per forzare Visual Basic a creare una stringa a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="1aafb-216">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="1aafb-217">Per impostazione predefinita, le stringhe sono di lunghezza variabile e questo attributo è utile quando si archiviano le stringhe nei file.</span><span class="sxs-lookup"><span data-stu-id="1aafb-217">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="1aafb-218">Il codice seguente illustra questo processo:</span><span class="sxs-lookup"><span data-stu-id="1aafb-218">The following code demonstrates this:</span></span>

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a><span data-ttu-id="1aafb-219">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="1aafb-219">VBFixedArrayAttribute</span></span>

<span data-ttu-id="1aafb-220">Utilizzare `VBFixedArrayAttribute` per dichiarare matrici di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="1aafb-220">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="1aafb-221">Come Visual Basic stringhe, le matrici hanno una lunghezza variabile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1aafb-221">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="1aafb-222">Questo attributo è utile per la serializzazione o la scrittura di dati in file.</span><span class="sxs-lookup"><span data-stu-id="1aafb-222">This attribute is useful when serializing or writing data to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="1aafb-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aafb-223">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="1aafb-224">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1aafb-224">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="1aafb-225">Attributi</span><span class="sxs-lookup"><span data-stu-id="1aafb-225">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="1aafb-226">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aafb-226">Reflection (Visual Basic)</span></span>](../reflection.md)
- [<span data-ttu-id="1aafb-227">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aafb-227">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](accessing-attributes-by-using-reflection.md)
