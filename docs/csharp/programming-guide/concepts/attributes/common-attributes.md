---
title: Attributi comuni (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 7988dad410c6e51869ec9d7e40d94e874443a5f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399756"
---
# <a name="common-attributes-c"></a><span data-ttu-id="27b1b-102">Attributi comuni (C#)</span><span class="sxs-lookup"><span data-stu-id="27b1b-102">Common Attributes (C#)</span></span>
<span data-ttu-id="27b1b-103">Questo argomento descrive gli attributi usati più di frequente nei programmi C#.</span><span class="sxs-lookup"><span data-stu-id="27b1b-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
- [<span data-ttu-id="27b1b-104">Attributi globali</span><span class="sxs-lookup"><span data-stu-id="27b1b-104">Global Attributes</span></span>](#Global)  
  
- [<span data-ttu-id="27b1b-105">Attributo Obsolete</span><span class="sxs-lookup"><span data-stu-id="27b1b-105">Obsolete Attribute</span></span>](#Obsolete)  
  
- [<span data-ttu-id="27b1b-106">Attributo condizionale</span><span class="sxs-lookup"><span data-stu-id="27b1b-106">Conditional Attribute</span></span>](#Conditional)  
  
- [<span data-ttu-id="27b1b-107">Attributi info chiamante</span><span class="sxs-lookup"><span data-stu-id="27b1b-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
## <a name="Global"></a><span data-ttu-id="27b1b-108">Attributi globali</span><span class="sxs-lookup"><span data-stu-id="27b1b-108">Global Attributes</span></span>  
 <span data-ttu-id="27b1b-109">La maggior parte degli attributi viene applicata a elementi specifici del linguaggio quali classi o metodi. Alcuni attributi sono invece globali e vengono applicati a un intero assembly o a un intero modulo.</span><span class="sxs-lookup"><span data-stu-id="27b1b-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="27b1b-110">Ad esempio, l'attributo <xref:System.Reflection.AssemblyVersionAttribute> può essere usato per incorporare informazioni sulla versione in un assembly, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="27b1b-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="27b1b-111">Gli attributi globali appaiono nel codice sorgente dopo eventuali direttive `using` di primo livello e prima delle dichiarazioni di tipo, modulo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="27b1b-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="27b1b-112">Gli attributi globali possono apparire in più file di origine, ma i file devono essere compilati in un'unica operazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="27b1b-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="27b1b-113">Nei progetti C# gli attributi globali vengono inseriti nel file AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="27b1b-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="27b1b-114">Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="27b1b-115">Sono suddivisi nelle seguenti categorie:</span><span class="sxs-lookup"><span data-stu-id="27b1b-115">They fall into the following categories:</span></span>  
  
- <span data-ttu-id="27b1b-116">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="27b1b-116">Assembly identity attributes</span></span>  
  
- <span data-ttu-id="27b1b-117">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="27b1b-117">Informational attributes</span></span>  
  
- <span data-ttu-id="27b1b-118">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="27b1b-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="27b1b-119">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="27b1b-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="27b1b-120">Tre attributi (con un nome sicuro, se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="27b1b-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="27b1b-121">Questi attributi formano il nome completo dell'assembly e sono necessari per creare riferimenti all'assembly nel codice.</span><span class="sxs-lookup"><span data-stu-id="27b1b-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="27b1b-122">È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="27b1b-123">Tuttavia il valore del nome viene impostato alla creazione dell'assembly dal compilatore (l'IDE di Visual Studio nella [finestra di dialogo informazioni Assembly](/visualstudio/ide/reference/assembly-information-dialog-box) oppure Assembly Linker, Al.exe), in base al file che contiene il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="27b1b-124">L'attributo <xref:System.Reflection.AssemblyFlagsAttribute> specifica se è supportata la coesistenza di più copie dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="27b1b-125">La tabella seguente visualizza gli attributi relativi all'identità.</span><span class="sxs-lookup"><span data-stu-id="27b1b-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="27b1b-126">Attributo</span><span class="sxs-lookup"><span data-stu-id="27b1b-126">Attribute</span></span>|<span data-ttu-id="27b1b-127">Scopo</span><span class="sxs-lookup"><span data-stu-id="27b1b-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="27b1b-128">Descrive in modo completo l'identità di un assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="27b1b-129">Specifica la versione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="27b1b-130">Specifica le impostazioni cultura supportate dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="27b1b-131">Specifica se un assembly supporta l'esecuzione side-by-side nello stesso computer, nello stesso processo o nello stesso dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27b1b-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="27b1b-132">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="27b1b-132">Informational Attributes</span></span>  
 <span data-ttu-id="27b1b-133">Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="27b1b-134">La tabella seguente mostra gli attributi informativi definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27b1b-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="27b1b-135">Attributo</span><span class="sxs-lookup"><span data-stu-id="27b1b-135">Attribute</span></span>|<span data-ttu-id="27b1b-136">Scopo</span><span class="sxs-lookup"><span data-stu-id="27b1b-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="27b1b-137">Definisce un attributo personalizzato che specifica un nome prodotto per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="27b1b-138">Definisce un attributo personalizzato che specifica un marchio registrato per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="27b1b-139">Definisce un attributo personalizzato che specifica una versione informativa per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="27b1b-140">Definisce un attributo personalizzato che specifica un nome società per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="27b1b-141">Definisce un attributo personalizzato che specifica un copyright per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="27b1b-142">Indica al compilatore di usare un numero di versione specifico per la risorsa della versione del file Win32.</span><span class="sxs-lookup"><span data-stu-id="27b1b-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="27b1b-143">Indica se l'assembly è conforme a CLS (Common Language Specification).</span><span class="sxs-lookup"><span data-stu-id="27b1b-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="27b1b-144">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="27b1b-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="27b1b-145">È possibile usare gli attributi relativi al manifesto dell'assembly per includere informazioni nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="27b1b-146">Queste informazioni includono il titolo, la descrizione, l'alias predefinito e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="27b1b-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="27b1b-147">La tabella seguente visualizza gli attributi del manifesto dell'assembly definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27b1b-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="27b1b-148">Attributo</span><span class="sxs-lookup"><span data-stu-id="27b1b-148">Attribute</span></span>|<span data-ttu-id="27b1b-149">Scopo</span><span class="sxs-lookup"><span data-stu-id="27b1b-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="27b1b-150">Definisce un attributo personalizzato che specifica un titolo assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="27b1b-151">Definisce un attributo personalizzato che specifica una descrizione assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="27b1b-152">Definisce un attributo personalizzato che specifica una configurazione assembly per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="27b1b-153">Definisce un alias predefinito descrittivo per un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="27b1b-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
## <a name="Obsolete"></a><span data-ttu-id="27b1b-154">Attributo Obsolete</span><span class="sxs-lookup"><span data-stu-id="27b1b-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="27b1b-155">L'attributo `Obsolete` contrassegna un'entità del programma il cui uso non è più consigliato.</span><span class="sxs-lookup"><span data-stu-id="27b1b-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="27b1b-156">Ogni uso di un'entità contrassegnata con Obsolete genererà in seguito un avviso o errore, a seconda della configurazione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="27b1b-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="27b1b-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="27b1b-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="27b1b-158">Nel seguente esempio l'attributo `Obsolete` viene applicato alla classe `A` e al metodo `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="27b1b-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="27b1b-159">Poiché il secondo argomento del costruttore dell'attributo applicato a `B.OldMethod` è impostato su `true` questo metodo genererà un errore del compilatore, mentre l'uso della classe `A` produrrà semplicemente un avviso.</span><span class="sxs-lookup"><span data-stu-id="27b1b-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="27b1b-160">Tuttavia la chiamata di `B.NewMethod` non produrrà né un avviso né un errore.</span><span class="sxs-lookup"><span data-stu-id="27b1b-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="27b1b-161">La stringa specificata come primo argomento al costruttore dell'attributo viene inclusa nell'avviso o nell'errore visualizzato.</span><span class="sxs-lookup"><span data-stu-id="27b1b-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="27b1b-162">Ad esempio, se viene usato con le definizioni precedenti, il codice che segue genera due avvisi e un errore:</span><span class="sxs-lookup"><span data-stu-id="27b1b-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="27b1b-163">Vengono generati due avvisi per la classe `A`: uno per la dichiarazione del riferimento alla classe e uno per il costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="27b1b-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="27b1b-164">L'attributo `Obsolete` può essere usato senza argomenti, ma è consigliabile includere la spiegazione del motivo per cui l'elemento è obsoleto e l'indicazione degli elementi di codice da usare come alternativa.</span><span class="sxs-lookup"><span data-stu-id="27b1b-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="27b1b-165">`Obsolete` è un attributo monouso e può essere applicato a qualsiasi entità che supporta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="27b1b-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="27b1b-166">`Obsolete` è un alias per <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="27b1b-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
## <a name="Conditional"></a> <span data-ttu-id="27b1b-167">Attributo Conditional</span><span class="sxs-lookup"><span data-stu-id="27b1b-167">Conditional Attribute</span></span>  
 <span data-ttu-id="27b1b-168">L'attributo `Conditional` rende l'esecuzione di un metodo dipendente da un identificatore di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="27b1b-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="27b1b-169">L'attributo `Conditional` è un alias per <xref:System.Diagnostics.ConditionalAttribute> e può essere applicato a un metodo o a una classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="27b1b-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="27b1b-170">In questo esempio, `Conditional` viene applicato a un metodo per attivare o disattivare la visualizzazione di informazioni di diagnostica specifiche del programma:</span><span class="sxs-lookup"><span data-stu-id="27b1b-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="27b1b-171">Se l'identificatore `TRACE_ON` non è definito, non viene visualizzato nessun output di traccia.</span><span class="sxs-lookup"><span data-stu-id="27b1b-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="27b1b-172">L'attributo `Conditional` viene usato spesso con l'identificatore `DEBUG` per abilitare funzioni di traccia e registrazione nelle compilazioni di debug ma non nelle build di rilascio, come segue:</span><span class="sxs-lookup"><span data-stu-id="27b1b-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="27b1b-173">Quando viene chiamato un metodo contrassegnato come condizionale, la presenza o l'assenza del simbolo di pre-elaborazione specificato determina se la chiamata viene inclusa o omessa.</span><span class="sxs-lookup"><span data-stu-id="27b1b-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="27b1b-174">Se il simbolo è definito la chiamata viene inclusa, in caso contrario viene omessa.</span><span class="sxs-lookup"><span data-stu-id="27b1b-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="27b1b-175">L'uso di `Conditional` rappresenta un'alternativa più efficiente, elegante e meno soggetta a errori rispetto all'inclusione di metodi nei blocchi `#if…#endif` come segue:</span><span class="sxs-lookup"><span data-stu-id="27b1b-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="27b1b-176">Un metodo condizionale deve essere un metodo in una dichiarazione di classe o struct e non deve avere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="27b1b-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="27b1b-177">Usare più identificatori</span><span class="sxs-lookup"><span data-stu-id="27b1b-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="27b1b-178">Se un metodo ha più attributi `Conditional`, una chiamata al metodo è inclusa se è definito almeno uno dei simboli condizionali (in altre parole, se i simboli sono collegati tra loro a livello logico mediante l'operatore OR).</span><span class="sxs-lookup"><span data-stu-id="27b1b-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="27b1b-179">In questo esempio la presenza di `A` o `B` determina una chiamata al metodo:</span><span class="sxs-lookup"><span data-stu-id="27b1b-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="27b1b-180">Per ottenere il collegamento logico di simboli tramite l'operatore AND è possibile definire metodi condizionali seriali.</span><span class="sxs-lookup"><span data-stu-id="27b1b-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="27b1b-181">Ad esempio, il secondo metodo riportato di seguito viene eseguito solo se sono definiti sia `A` sia `B`:</span><span class="sxs-lookup"><span data-stu-id="27b1b-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="27b1b-182">Usare Conditional con le classi di attributi</span><span class="sxs-lookup"><span data-stu-id="27b1b-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="27b1b-183">L'attributo `Conditional` può essere applicato anche a una definizione di classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="27b1b-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="27b1b-184">In questo esempio l'attributo personalizzato `Documentation` aggiunge le informazioni ai metadati solo se è definito l'elemento DEBUG.</span><span class="sxs-lookup"><span data-stu-id="27b1b-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
## <a name="CallerInfo"></a><span data-ttu-id="27b1b-185">Attributi info chiamante</span><span class="sxs-lookup"><span data-stu-id="27b1b-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="27b1b-186">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="27b1b-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="27b1b-187">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="27b1b-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="27b1b-188">È possibile ottenere informazioni sul chiamante usando gli attributi applicati ai parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="27b1b-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="27b1b-189">Ogni parametro facoltativo specifica un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="27b1b-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="27b1b-190">Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="27b1b-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="27b1b-191">Attributo</span><span class="sxs-lookup"><span data-stu-id="27b1b-191">Attribute</span></span>|<span data-ttu-id="27b1b-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27b1b-192">Description</span></span>|<span data-ttu-id="27b1b-193">Type</span><span class="sxs-lookup"><span data-stu-id="27b1b-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="27b1b-194">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="27b1b-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="27b1b-195">È il percorso al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="27b1b-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="27b1b-196">Numero di riga nel file di origine da cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="27b1b-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="27b1b-197">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="27b1b-197">Method name or property name of the caller.</span></span> <span data-ttu-id="27b1b-198">Per altre informazioni, vedere [Informazioni sul chiamante (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="27b1b-198">For more information, see [Caller Information (C#)](../caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="27b1b-199">Per altre informazioni sugli attributi di informazioni sul chiamante, vedere [Informazioni sul chiamante (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="27b1b-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b1b-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27b1b-200">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="27b1b-201">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="27b1b-201">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="27b1b-202">Attributi</span><span class="sxs-lookup"><span data-stu-id="27b1b-202">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="27b1b-203">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="27b1b-203">Reflection (C#)</span></span>](../reflection.md)
- <span data-ttu-id="27b1b-204">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="27b1b-204">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md)</span></span>
