---
title: Indipendenza del linguaggio e componenti indipendenti dal linguaggio
description: Informazioni su come sviluppare in uno dei molti linguaggi supportati in .NET, ad esempio C#, C++/interfaccia della riga di comando, F#, IronPython, VB, Visual COBOL e PowerShell.
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: 813558299b40e0b90e8047f22b788c8f1419eb5e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504654"
---
# <a name="language-independence-and-language-independent-components"></a><span data-ttu-id="ade0a-103">Indipendenza del linguaggio e componenti indipendenti dal linguaggio</span><span class="sxs-lookup"><span data-stu-id="ade0a-103">Language independence and language-independent components</span></span>

<span data-ttu-id="ade0a-104">.NET è indipendente dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ade0a-104">.NET is language independent.</span></span> <span data-ttu-id="ade0a-105">Questo significa che gli sviluppatori possono lavorare in uno dei diversi linguaggi che hanno come destinazione le implementazioni di .NET, ad esempio C#, F# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ade0a-105">This means that, as a developer, you can develop in one of the many languages that target .NET implementations, such as C#, F#, and Visual Basic.</span></span> <span data-ttu-id="ade0a-106">È possibile accedere a tipi e membri di librerie di classi sviluppate per le implementazioni di .NET senza dover conoscere il linguaggio in cui sono stati originariamente scritti e senza dover seguire nessuna delle convenzioni del linguaggio originale.</span><span class="sxs-lookup"><span data-stu-id="ade0a-106">You can access the types and members of class libraries developed for .NET implementations without having to know the language in which they were originally written and without having to follow any of the original language's conventions.</span></span> <span data-ttu-id="ade0a-107">Se si è uno sviluppatore di componenti, è possibile accedere al componente da qualsiasi applicazione .NET, indipendentemente dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ade0a-107">If you're a component developer, your component can be accessed by any .NET app, regardless of its language.</span></span>

> [!NOTE]
> <span data-ttu-id="ade0a-108">Questa prima parte di questo articolo illustra la creazione di componenti indipendenti dal linguaggio, ovvero componenti che possono essere usati da app scritte in qualsiasi linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ade0a-108">This first part of this article discusses creating language-independent components, that is, components that can be consumed by apps that are written in any language.</span></span> <span data-ttu-id="ade0a-109">È anche possibile creare un singolo componente o applicazione dal codice sorgente scritto in più linguaggi. Vedere [Interoperabilità tra linguaggi diversi](#cross-language-interoperability) nella seconda parte di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-109">You can also create a single component or app from source code written in multiple languages; see [Cross-Language Interoperability](#cross-language-interoperability) in the second part of this article.</span></span>

<span data-ttu-id="ade0a-110">È necessario che gli oggetti espongano ai chiamanti solo le funzionalità comuni a tutti i linguaggi, affinché sia garantita un'interazione completa con altri oggetti scritti in uno qualsiasi dei linguaggi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-110">To fully interact with other objects written in any language, objects must expose to callers only those features that are common to all languages.</span></span> <span data-ttu-id="ade0a-111">Questo set comune di funzionalità è definito dalle specifiche CLS (Common Language Specification), un set di regole che si applicano agli assembly generati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-111">This common set of features is defined by the Common Language Specification (CLS), which is a set of rules that apply to generated assemblies.</span></span> <span data-ttu-id="ade0a-112">Le specifiche CLS (Common Language Specification) sono definite nella partizione I, clausole da 7 a 11 dello [standard ECMA-335 di Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ade0a-112">The Common Language Specification is defined in Partition I, Clauses 7 through 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

<span data-ttu-id="ade0a-113">Se il componente è conforme alle specifiche CLS (Common Language Specification), ne è garantita la conformità a CLS ed è possibile accedervi dal codice negli assembly scritti in qualsiasi linguaggio di programmazione che supporti CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-113">If your component conforms to the Common Language Specification, it is guaranteed to be CLS-compliant and can be accessed from code in assemblies written in any programming language that supports the CLS.</span></span> <span data-ttu-id="ade0a-114">È possibile determinare se il componente è conforme alle specifiche CLS (Common Language Specification) in fase di compilazione applicando l'attributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ade0a-114">You can determine whether your component conforms to the Common Language Specification at compile time by applying the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute to your source code.</span></span> <span data-ttu-id="ade0a-115">Per altre informazioni, vedere [Attributo CLSCompliantAttribute](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="ade0a-115">For more information, see [The CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute).</span></span>

## <a name="cls-compliance-rules"></a><span data-ttu-id="ade0a-116">Regole di conformità a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-116">CLS compliance rules</span></span>

<span data-ttu-id="ade0a-117">In questa sezione vengono illustrate le regole per creare un componente conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-117">This section discusses the rules for creating a CLS-compliant component.</span></span> <span data-ttu-id="ade0a-118">Per un elenco completo delle regole, vedere la partizione I, clausola 11 dello [standard ECMA-335 di Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ade0a-118">For a complete list of rules, see Partition I, Clause 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="ade0a-119">Nelle specifiche CLS (Common Language Specification) viene illustrata ciascuna regola per la conformità a CLS applicata ai consumer (sviluppatori che accedono a livello di codice a un componente conforme a CLS), ai framework (sviluppatori che usano un compilatore di linguaggio per creare librerie conformi a CLS) e alle estensioni (sviluppatori che creano uno strumento quale un compilatore di linguaggio o un parser di codice per la creazione di componenti conformi a CLS).</span><span class="sxs-lookup"><span data-stu-id="ade0a-119">The Common Language Specification discusses each rule for CLS compliance as it applies to consumers (developers who are programmatically accessing a component that is CLS-compliant), frameworks (developers who are using a language compiler to create CLS-compliant libraries), and extenders (developers who are creating a tool such as a language compiler or a code parser that creates CLS-compliant components).</span></span> <span data-ttu-id="ade0a-120">Questo articolo è incentrato sulle regole che si applicano ai framework.</span><span class="sxs-lookup"><span data-stu-id="ade0a-120">This article focuses on the rules as they apply to frameworks.</span></span> <span data-ttu-id="ade0a-121">Si noti, tuttavia, che alcune delle regole applicate alle estensioni possono essere applicate anche agli assembly creati mediante [Reflection. Emit](xref:System.Reflection.Emit).</span><span class="sxs-lookup"><span data-stu-id="ade0a-121">Note, though, that some of the rules that apply to extenders may also apply to assemblies that are created using [Reflection.Emit](xref:System.Reflection.Emit).</span></span>

<span data-ttu-id="ade0a-122">Per progettare un componente indipendente dal linguaggio, è necessario applicare le regole per la conformità a CLS solo all'interfaccia pubblica del componente.</span><span class="sxs-lookup"><span data-stu-id="ade0a-122">To design a component that is language independent, you only need to apply the rules for CLS compliance to your component's public interface.</span></span> <span data-ttu-id="ade0a-123">L'implementazione privata non deve essere conforme alla specifica.</span><span class="sxs-lookup"><span data-stu-id="ade0a-123">Your private implementation does not have to conform to the specification.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ade0a-124">Le regole per la conformità a CLS si applicano solo all'interfaccia pubblica di un componente, non alla relativa implementazione privata.</span><span class="sxs-lookup"><span data-stu-id="ade0a-124">The rules for CLS compliance apply only to a component's public interface, not to its private implementation.</span></span>

<span data-ttu-id="ade0a-125">Ad esempio, Unsigned Integer diversi da [Byte](xref:System.Byte) non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-125">For example, unsigned integers other than [Byte](xref:System.Byte) are not CLS-compliant.</span></span> <span data-ttu-id="ade0a-126">Poiché la classe `Person` dell'esempio seguente espone una proprietà `Age` di tipo [UInt16](xref:System.UInt16), il codice riportato di seguito visualizza un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-126">Because the `Person` class in the following example exposes an `Age` property of type [UInt16](xref:System.UInt16), the following code displays a compiler warning.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

<span data-ttu-id="ade0a-127">È possibile rendere la classe Person conforme a CLS modificando il tipo di proprietà `Age` da `UInt16` a [Int16](xref:System.Int16), vale a dire un Signed Integer a 16 bit conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-127">You can make the Person class CLS-compliant by changing the type of `Age` property from `UInt16` to [Int16](xref:System.Int16), which is a CLS-compliant, 16-bit signed integer.</span></span> <span data-ttu-id="ade0a-128">Non è necessario modificare il tipo del campo `personAge` privato.</span><span class="sxs-lookup"><span data-stu-id="ade0a-128">You do not have to change the type of the private `personAge` field.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

<span data-ttu-id="ade0a-129">L'interfaccia pubblica di una libreria è costituita dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ade0a-129">A library's public interface consists of the following:</span></span>

* <span data-ttu-id="ade0a-130">Definizioni di classi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="ade0a-130">Definitions of public classes.</span></span>

* <span data-ttu-id="ade0a-131">Definizioni dei membri pubblici di classi pubbliche e definizioni di membri accessibili alle classi derivate, cioè membri protetti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-131">Definitions of the public members of public classes, and definitions of members accessible to derived classes (that is, protected members).</span></span>

* <span data-ttu-id="ade0a-132">Parametri e tipi restituiti di metodi pubblici di classi pubbliche e parametri e tipi restituiti di metodi accessibili alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="ade0a-132">Parameters and return types of public methods of public classes, and parameters and return types of methods accessible to derived classes.</span></span>

<span data-ttu-id="ade0a-133">Le regole per la conformità a CLS sono elencate nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-133">The rules for CLS compliance are listed in the following table.</span></span> <span data-ttu-id="ade0a-134">Il testo delle regole è stato copiato alla lettera dallo [standard ECMA-335 di Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), Copyright 2012 di Ecma International.</span><span class="sxs-lookup"><span data-stu-id="ade0a-134">The text of the rules is taken verbatim from the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), which is Copyright 2012 by Ecma International.</span></span> <span data-ttu-id="ade0a-135">Nelle sezioni seguenti sono disponibili informazioni più dettagliate su queste regole.</span><span class="sxs-lookup"><span data-stu-id="ade0a-135">More detailed information about these rules is found in the following sections.</span></span>

<span data-ttu-id="ade0a-136">Category</span><span class="sxs-lookup"><span data-stu-id="ade0a-136">Category</span></span> | <span data-ttu-id="ade0a-137">Vedere</span><span class="sxs-lookup"><span data-stu-id="ade0a-137">See</span></span> | <span data-ttu-id="ade0a-138">Regola</span><span class="sxs-lookup"><span data-stu-id="ade0a-138">Rule</span></span> | <span data-ttu-id="ade0a-139">Numero regola</span><span class="sxs-lookup"><span data-stu-id="ade0a-139">Rule Number</span></span>
-------- | --- | ---- | -----------
<span data-ttu-id="ade0a-140">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="ade0a-140">Accessibility</span></span> | [<span data-ttu-id="ade0a-141">Accessibilità del membro</span><span class="sxs-lookup"><span data-stu-id="ade0a-141">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="ade0a-142">L'accessibilità non sarà modificata quando si esegue l'override di metodi ereditati, tranne nel caso in cui si esegue l'override di un metodo ereditato da un assembly diverso con accessibilità `family-or-assembly`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-142">Accessibility shall not be changed when overriding inherited methods, except when overriding a method inherited from a different assembly with accessibility `family-or-assembly`.</span></span> <span data-ttu-id="ade0a-143">In questo caso, l'override disporrà dell'accessibilità `family`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-143">In this case, the override shall have accessibility `family`.</span></span> | <span data-ttu-id="ade0a-144">10</span><span class="sxs-lookup"><span data-stu-id="ade0a-144">10</span></span>
<span data-ttu-id="ade0a-145">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="ade0a-145">Accessibility</span></span> | [<span data-ttu-id="ade0a-146">Accessibilità del membro</span><span class="sxs-lookup"><span data-stu-id="ade0a-146">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="ade0a-147">La visibilità e l'accessibilità di tipi e membri saranno tali che i tipi nella firma di qualsiasi membro saranno visibili e accessibili ogni volta che il membro stesso è visibile e accessibile.</span><span class="sxs-lookup"><span data-stu-id="ade0a-147">The visibility and accessibility of types and members shall be such that types in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="ade0a-148">Ad esempio, in un metodo pubblico che è visibile all'esterno del relativo assembly non deve essere presente un argomento il cui tipo è visibile solo nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ade0a-148">For example, a public method that is visible outside its assembly shall not have an argument whose type is visible only within the assembly.</span></span> <span data-ttu-id="ade0a-149">La visibilità e l'accessibilità di tipi che compongono un tipo generico con istanze usato nella firma di qualsiasi membro saranno visibili e accessibili ogni volta che il membro stesso è visibile e accessibile.</span><span class="sxs-lookup"><span data-stu-id="ade0a-149">The visibility and accessibility of types composing an instantiated generic type used in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="ade0a-150">Ad esempio, in un tipo generico con istanze presente nella firma di un membro visibile all'esterno del relativo assembly non deve essere disponibile un argomento generico il cui tipo è visibile solo nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ade0a-150">For example, an instantiated generic type present in the signature of a member that is visible outside its assembly shall not have a generic argument whose type is visible only within the assembly.</span></span> | <span data-ttu-id="ade0a-151">12</span><span class="sxs-lookup"><span data-stu-id="ade0a-151">12</span></span>
<span data-ttu-id="ade0a-152">Matrici</span><span class="sxs-lookup"><span data-stu-id="ade0a-152">Arrays</span></span> | [<span data-ttu-id="ade0a-153">Matrici</span><span class="sxs-lookup"><span data-stu-id="ade0a-153">Arrays</span></span>](#arrays) | <span data-ttu-id="ade0a-154">Le matrici devono disporre di elementi con un tipo conforme a CLS e i limiti inferiori di tutte le dimensioni della matrice devono essere pari a zero.</span><span class="sxs-lookup"><span data-stu-id="ade0a-154">Arrays shall have elements with a CLS-compliant type, and all dimensions of the array shall have lower bounds of zero.</span></span> <span data-ttu-id="ade0a-155">Solo per il fatto che un elemento sia una matrice, il tipo di elemento della matrice sarà richiesto per eseguire una distinzione tra gli overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-155">Only the fact that an item is an array and the element type of the array shall be required to distinguish between overloads.</span></span> <span data-ttu-id="ade0a-156">Quando l'overload è basato su due o più tipi di matrice, i tipi di elemento devono essere tipi denominati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-156">When overloading is based on two or more array types, the element types shall be named types.</span></span> | <span data-ttu-id="ade0a-157">16</span><span class="sxs-lookup"><span data-stu-id="ade0a-157">16</span></span>
<span data-ttu-id="ade0a-158">Attributi</span><span class="sxs-lookup"><span data-stu-id="ade0a-158">Attributes</span></span> | [<span data-ttu-id="ade0a-159">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="ade0a-159">Attributes</span></span>](#attributes) | <span data-ttu-id="ade0a-160">Gli attributi devono essere di tipo [System.Attribute](xref:System.Attribute) o derivati da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-160">Attributes shall be of type [System.Attribute](xref:System.Attribute), or a type inheriting from it.</span></span> | <span data-ttu-id="ade0a-161">41</span><span class="sxs-lookup"><span data-stu-id="ade0a-161">41</span></span>
<span data-ttu-id="ade0a-162">Attributi</span><span class="sxs-lookup"><span data-stu-id="ade0a-162">Attributes</span></span> | [<span data-ttu-id="ade0a-163">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="ade0a-163">Attributes</span></span>](#attributes) | <span data-ttu-id="ade0a-164">La specifica CLS consente solo un subset delle codifiche di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-164">The CLS only allows a subset of the encodings of custom attributes.</span></span> <span data-ttu-id="ade0a-165">Gli unici tipi che verranno visualizzati in queste codifiche sono (vedere la partizione IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) e qualsiasi tipo di enumerazione basato su un tipo Integer di base conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-165">The only types that shall appear in these encodings are (see Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double), and any enumeration type based on a CLS-compliant base integer type.</span></span> | <span data-ttu-id="ade0a-166">34</span><span class="sxs-lookup"><span data-stu-id="ade0a-166">34</span></span>
<span data-ttu-id="ade0a-167">Attributi</span><span class="sxs-lookup"><span data-stu-id="ade0a-167">Attributes</span></span> | [<span data-ttu-id="ade0a-168">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="ade0a-168">Attributes</span></span>](#attributes) | <span data-ttu-id="ade0a-169">La specifica CLS non consente i modificatori necessari visibili pubblicamente (`modreq`, vedere la partizione II), ma consente i modificatori facoltativi (`modopt`, vedere la partizione II) che non riconosce.</span><span class="sxs-lookup"><span data-stu-id="ade0a-169">The CLS does not allow publicly visible required modifiers (`modreq`, see Partition II), but does allow optional modifiers (`modopt`, see Partition II) it does not understand.</span></span> | <span data-ttu-id="ade0a-170">35</span><span class="sxs-lookup"><span data-stu-id="ade0a-170">35</span></span>
<span data-ttu-id="ade0a-171">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-171">Constructors</span></span> | [<span data-ttu-id="ade0a-172">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-172">Constructors</span></span>](#constructors) | <span data-ttu-id="ade0a-173">Prima di un eventuale accesso ai dati di istanza ereditati, tramite un costruttore di oggetti deve essere effettuata una chiamata a un costruttore di istanze della relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="ade0a-173">An object constructor shall call some instance constructor of its base class before any access occurs to inherited instance data.</span></span> <span data-ttu-id="ade0a-174">Ciò non si applica ai tipi di valore, che non devono disporre di costruttori.</span><span class="sxs-lookup"><span data-stu-id="ade0a-174">(This does not apply to value types, which need not have constructors.)</span></span>  | <span data-ttu-id="ade0a-175">21</span><span class="sxs-lookup"><span data-stu-id="ade0a-175">21</span></span>
<span data-ttu-id="ade0a-176">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-176">Constructors</span></span> | [<span data-ttu-id="ade0a-177">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-177">Constructors</span></span>](#constructors) | <span data-ttu-id="ade0a-178">Un costruttore di oggetti non deve essere chiamato se non come parte della creazione di un oggetto e un oggetto non deve essere inizializzato due volte.</span><span class="sxs-lookup"><span data-stu-id="ade0a-178">An object constructor shall not be called except as part of the creation of an object, and an object shall not be initialized twice.</span></span> | <span data-ttu-id="ade0a-179">22</span><span class="sxs-lookup"><span data-stu-id="ade0a-179">22</span></span>
<span data-ttu-id="ade0a-180">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-180">Enumerations</span></span> | [<span data-ttu-id="ade0a-181">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-181">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ade0a-182">Il tipo sottostante di un'enumerazione deve essere un tipo Integer CLS incorporato, il nome del campo deve essere "value__" e il campo deve essere contrassegnato come `RTSpecialName`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-182">The underlying type of an enum shall be a built-in CLS integer type, the name of the field shall be "value__", and that field shall be marked `RTSpecialName`.</span></span> |  <span data-ttu-id="ade0a-183">7</span><span class="sxs-lookup"><span data-stu-id="ade0a-183">7</span></span>
<span data-ttu-id="ade0a-184">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-184">Enumerations</span></span> | [<span data-ttu-id="ade0a-185">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-185">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ade0a-186">Sono disponibili due tipi distinti di enumerazioni, indicati dalla presenza o dall'assenza dell'attributo personalizzato [System.FlagsAttribute](xref:System.FlagsAttribute) (vedere la libreria nella partizione IV).</span><span class="sxs-lookup"><span data-stu-id="ade0a-186">There are two distinct kinds of enums, indicated by the presence or absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) (see Partition IV Library) custom attribute.</span></span> <span data-ttu-id="ade0a-187">Una rappresenta Integer denominati, l'altra flag di bit denominati che possono essere combinati per generare un valore senza nome.</span><span class="sxs-lookup"><span data-stu-id="ade0a-187">One represents named integer values; the other represents named bit flags that can be combined to generate an unnamed value.</span></span> <span data-ttu-id="ade0a-188">Il valore di un oggetto `enum` non è limitato ai valori specifici.</span><span class="sxs-lookup"><span data-stu-id="ade0a-188">The value of an `enum` is not limited to the specified values.</span></span> |  <span data-ttu-id="ade0a-189">8</span><span class="sxs-lookup"><span data-stu-id="ade0a-189">8</span></span>
<span data-ttu-id="ade0a-190">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-190">Enumerations</span></span> | [<span data-ttu-id="ade0a-191">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-191">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ade0a-192">Il tipo dei campi statici con valori letterali di un'enumerazione deve essere uguale a quello dell'enumerazione stessa.</span><span class="sxs-lookup"><span data-stu-id="ade0a-192">Literal static fields of an enum shall have the type of the enum itself.</span></span> |  <span data-ttu-id="ade0a-193">9</span><span class="sxs-lookup"><span data-stu-id="ade0a-193">9</span></span>
<span data-ttu-id="ade0a-194">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-194">Events</span></span> | [<span data-ttu-id="ade0a-195">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-195">Events</span></span>](#events) | <span data-ttu-id="ade0a-196">I metodi che implementano un evento devono essere contrassegnati come `SpecialName` nei metadati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-196">The methods that implement an event shall be marked `SpecialName` in the metadata.</span></span> |<span data-ttu-id="ade0a-197">29</span><span class="sxs-lookup"><span data-stu-id="ade0a-197">29</span></span>
<span data-ttu-id="ade0a-198">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-198">Events</span></span> | [<span data-ttu-id="ade0a-199">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-199">Events</span></span>](#events) | <span data-ttu-id="ade0a-200">L'accessibilità di un evento e le relative funzioni di accesso devono essere identiche.</span><span class="sxs-lookup"><span data-stu-id="ade0a-200">The accessibility of an event and of its accessors shall be identical.</span></span> |<span data-ttu-id="ade0a-201">30</span><span class="sxs-lookup"><span data-stu-id="ade0a-201">30</span></span>
<span data-ttu-id="ade0a-202">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-202">Events</span></span> | [<span data-ttu-id="ade0a-203">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-203">Events</span></span>](#events) | <span data-ttu-id="ade0a-204">I metodi `add` e `remove` per un evento devono essere entrambi presenti o entrambi assenti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-204">The `add` and `remove` methods for an event shall both either be present or absent.</span></span> |<span data-ttu-id="ade0a-205">31</span><span class="sxs-lookup"><span data-stu-id="ade0a-205">31</span></span>
<span data-ttu-id="ade0a-206">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-206">Events</span></span> | [<span data-ttu-id="ade0a-207">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-207">Events</span></span>](#events) | <span data-ttu-id="ade0a-208">I `add` `remove` metodi e per un evento devono entrambi assumere un parametro il cui tipo definisce il tipo dell'evento e che deve essere derivato da [System. Delegate](xref:System.Delegate).</span><span class="sxs-lookup"><span data-stu-id="ade0a-208">The `add` and `remove` methods for an event shall each take one parameter whose type defines the type of the event and that shall be derived from [System.Delegate](xref:System.Delegate).</span></span> |<span data-ttu-id="ade0a-209">32</span><span class="sxs-lookup"><span data-stu-id="ade0a-209">32</span></span>
<span data-ttu-id="ade0a-210">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-210">Events</span></span> | [<span data-ttu-id="ade0a-211">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-211">Events</span></span>](#events) | <span data-ttu-id="ade0a-212">Gli eventi devono essere conformi a un pattern di nome specifico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-212">Events shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="ade0a-213">L'attributo SpecialName indicato nella regola CLS 29 deve essere ignorato nei confronti tra nomi appropriati e deve essere conforme alle regole dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-213">The SpecialName attribute referred to in CLS rule 29 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span>  |<span data-ttu-id="ade0a-214">33</span><span class="sxs-lookup"><span data-stu-id="ade0a-214">33</span></span>
<span data-ttu-id="ade0a-215">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-215">Exceptions</span></span> | [<span data-ttu-id="ade0a-216">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-216">Exceptions</span></span>](#exceptions) | <span data-ttu-id="ade0a-217">Gli oggetti generati devono essere di tipo [System.Exception](xref:System.Exception) o di un tipo che eredita da esso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-217">Objects that are thrown shall be of type [System.Exception](xref:System.Exception) or a type inheriting from it.</span></span> <span data-ttu-id="ade0a-218">Ciononostante, i metodi conformi a CLS non sono necessari per bloccare la propagazione di altri tipi di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ade0a-218">Nonetheless, CLS-compliant methods are not required to block the propagation of other types of exceptions.</span></span> | <span data-ttu-id="ade0a-219">40</span><span class="sxs-lookup"><span data-stu-id="ade0a-219">40</span></span>
<span data-ttu-id="ade0a-220">Generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-220">General</span></span> | [<span data-ttu-id="ade0a-221">Regole di conformità a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-221">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="ade0a-222">Le regole CLS sono valide solo per le parti di un tipo che sono accessibili o visibili all'esterno dell'assembly di definizione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-222">CLS rules apply only to those parts of a type that are accessible or visible outside of the defining assembly.</span></span> | <span data-ttu-id="ade0a-223">1</span><span class="sxs-lookup"><span data-stu-id="ade0a-223">1</span></span>
<span data-ttu-id="ade0a-224">Generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-224">General</span></span> | [<span data-ttu-id="ade0a-225">Regole di conformità a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-225">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="ade0a-226">I membri di tipi non conformi a CLS non saranno contrassegnati come conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-226">Members of non-CLS compliant types shall not be marked CLS-compliant.</span></span> | <span data-ttu-id="ade0a-227">2</span><span class="sxs-lookup"><span data-stu-id="ade0a-227">2</span></span>
<span data-ttu-id="ade0a-228">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-228">Generics</span></span> | [<span data-ttu-id="ade0a-229">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-229">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-230">I tipi annidati disporranno di un numero di parametri generici almeno pari a quelli del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-230">Nested types shall have at least as many generic parameters as the enclosing type.</span></span> <span data-ttu-id="ade0a-231">I parametri generici di un tipo annidato corrispondono per posizione ai parametri generici del rispettivo tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-231">Generic parameters in a nested type correspond by position to the generic parameters in its enclosing type.</span></span>  | <span data-ttu-id="ade0a-232">42</span><span class="sxs-lookup"><span data-stu-id="ade0a-232">42</span></span>
<span data-ttu-id="ade0a-233">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-233">Generics</span></span> | [<span data-ttu-id="ade0a-234">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-234">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-235">Con il nome di un tipo generico verrà codificato il numero di parametri di tipo dichiarati nel tipo non annidato o appena introdotti nel tipo se annidato, in base alle regole definite sopra.</span><span class="sxs-lookup"><span data-stu-id="ade0a-235">The name of a generic type shall encode the number of type parameters declared on the non-nested type, or newly introduced to the type if nested, according to the rules defined above.</span></span> | <span data-ttu-id="ade0a-236">43</span><span class="sxs-lookup"><span data-stu-id="ade0a-236">43</span></span>
<span data-ttu-id="ade0a-237">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-237">Generics</span></span> | [<span data-ttu-id="ade0a-238">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-238">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-239">Tramite un tipo generico deve essere dichiarato nuovamente un numero di vincoli sufficiente a garantire che qualsiasi vincolo delle interfacce o del tipo base venga soddisfatto dai vincoli del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-239">A generic type shall redeclare sufficient constraints to guarantee that any constraints on the base type, or interfaces would be satisfied by the generic type constraints.</span></span> | <span data-ttu-id="ade0a-240">44</span><span class="sxs-lookup"><span data-stu-id="ade0a-240">44</span></span>
<span data-ttu-id="ade0a-241">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-241">Generics</span></span> | [<span data-ttu-id="ade0a-242">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-242">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-243">I tipi usati come vincoli sui parametri generici dovranno essere essi stessi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-243">Types used as constraints on generic parameters shall themselves be CLS-compliant.</span></span> | <span data-ttu-id="ade0a-244">45</span><span class="sxs-lookup"><span data-stu-id="ade0a-244">45</span></span>
<span data-ttu-id="ade0a-245">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-245">Generics</span></span> | [<span data-ttu-id="ade0a-246">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-246">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-247">La visibilità e l'accessibilità di membri (compresi i tipi annidati) in un tipo generico con istanze devono essere considerate come limitate all'ambito della creazione di un'istanza specifica, anziché come dichiarazione del tipo generico nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-247">The visibility and accessibility of members (including nested types) in an instantiated generic type shall be considered to be scoped to the specific instantiation rather than the generic type declaration as a whole.</span></span> <span data-ttu-id="ade0a-248">Partendo da questo presupposto, valgono ancora le regole di visibilità e accessibilità della regola CLS 12.</span><span class="sxs-lookup"><span data-stu-id="ade0a-248">Assuming this, the visibility and accessibility rules of CLS rule 12 still apply.</span></span> | <span data-ttu-id="ade0a-249">46</span><span class="sxs-lookup"><span data-stu-id="ade0a-249">46</span></span>
<span data-ttu-id="ade0a-250">Generics</span><span class="sxs-lookup"><span data-stu-id="ade0a-250">Generics</span></span> | [<span data-ttu-id="ade0a-251">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-251">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ade0a-252">Per ogni metodo generico astratto o virtuale sarà necessaria un'implementazione concreta (non astratta) predefinita</span><span class="sxs-lookup"><span data-stu-id="ade0a-252">For each abstract or virtual generic method, there shall be a default concrete (nonabstract) implementation</span></span> | <span data-ttu-id="ade0a-253">47</span><span class="sxs-lookup"><span data-stu-id="ade0a-253">47</span></span>
<span data-ttu-id="ade0a-254">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-254">Interfaces</span></span> | [<span data-ttu-id="ade0a-255">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-255">Interfaces</span></span>](#interfaces) | <span data-ttu-id="ade0a-256">Per l'implementazione delle interfacce conformi a CLS, non sarà necessaria la definizione di metodi non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-256">CLS-compliant interfaces shall not require the definition of non-CLS compliant methods in order to implement them.</span></span> | <span data-ttu-id="ade0a-257">18</span><span class="sxs-lookup"><span data-stu-id="ade0a-257">18</span></span>
<span data-ttu-id="ade0a-258">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-258">Interfaces</span></span> | [<span data-ttu-id="ade0a-259">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-259">Interfaces</span></span>](#interfaces) | <span data-ttu-id="ade0a-260">Tramite le interfacce conformi a CLS non verranno definiti i metodi statici, né verranno definiti i campi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-260">CLS-compliant interfaces shall not define static methods, nor shall they define fields.</span></span> | <span data-ttu-id="ade0a-261">19</span><span class="sxs-lookup"><span data-stu-id="ade0a-261">19</span></span>
<span data-ttu-id="ade0a-262">Membri</span><span class="sxs-lookup"><span data-stu-id="ade0a-262">Members</span></span> | [<span data-ttu-id="ade0a-263">Membri dei tipi di in generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-263">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="ade0a-264">I metodi e i campi static globali non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-264">Global static fields and methods are not CLS-compliant.</span></span> | <span data-ttu-id="ade0a-265">36</span><span class="sxs-lookup"><span data-stu-id="ade0a-265">36</span></span>
<span data-ttu-id="ade0a-266">Membri</span><span class="sxs-lookup"><span data-stu-id="ade0a-266">Members</span></span> | -- | <span data-ttu-id="ade0a-267">Il valore di un valore statico letterale viene specificato attraverso l'uso dei metadati di inizializzazione del campo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-267">The value of a literal static is specified through the use of field initialization metadata.</span></span> <span data-ttu-id="ade0a-268">Un valore letterale conforme a CLS deve disporre di un valore specificato nei metadati di inizializzazione del campo che sia esattamente dello stesso tipo del valore letterale, o del tipo sottostante, se questo valore letterale è un oggetto `enum`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-268">A CLS-compliant literal must have a value specified in field initialization metadata that is of exactly the same type as the literal (or of the underlying type, if that literal is an `enum`).</span></span> | <span data-ttu-id="ade0a-269">13</span><span class="sxs-lookup"><span data-stu-id="ade0a-269">13</span></span>
<span data-ttu-id="ade0a-270">Membri</span><span class="sxs-lookup"><span data-stu-id="ade0a-270">Members</span></span> | [<span data-ttu-id="ade0a-271">Membri dei tipi di in generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-271">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="ade0a-272">Il vincolo vararg non fa parte delle specifiche CLS e l'unica convenzione di chiamata supportata da CLS è la convenzione di chiamata gestita standard.</span><span class="sxs-lookup"><span data-stu-id="ade0a-272">The vararg constraint is not part of the CLS, and the only calling convention supported by the CLS is the standard managed calling convention.</span></span> | <span data-ttu-id="ade0a-273">15</span><span class="sxs-lookup"><span data-stu-id="ade0a-273">15</span></span>
<span data-ttu-id="ade0a-274">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-274">Naming conventions</span></span> | [<span data-ttu-id="ade0a-275">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-275">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ade0a-276">Gli assembly seguiranno l'allegato 7 del rapporto tecnico 15 di Unicode Standard 3.0 con cui viene controllato il set di caratteri che possono essere usati all'inizio e all'interno degli identificatori, disponibili online nella pagina [Unicode Normalization Forms](https://unicode.org/reports/tr15/) (Formati di normalizzazione Unicode).</span><span class="sxs-lookup"><span data-stu-id="ade0a-276">Assemblies shall follow Annex 7 of Technical Report 15 of the Unicode Standard3.0 governing the set of characters permitted to start and be included in identifiers, available online at [Unicode Normalization Forms](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="ade0a-277">Gli identificatori dovranno essere nel formato canonico definito dal formato di normalizzazione Unicode C. Per scopi correlati a CLS, due identificatori sono identici se i rispettivi mapping delle minuscole (come specificato dai mapping di minuscole di tipo uno a uno, senza distinzione tra le impostazioni locali Unicode) sono uguali.</span><span class="sxs-lookup"><span data-stu-id="ade0a-277">Identifiers shall be in the canonical format defined by Unicode Normalization Form C. For CLS purposes, two identifiers are the same if their lowercase mappings (as specified by the Unicode locale-insensitive, one-to-one lowercase mappings) are the same.</span></span> <span data-ttu-id="ade0a-278">Vale a dire, affinché due identificatori vengano considerati differenti nella specifica CLS, devono presentare differenze che vanno oltre la semplice distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ade0a-278">That is, for two identifiers to be considered different under the CLS they shall differ in more than simply their case.</span></span> <span data-ttu-id="ade0a-279">Tuttavia, per eseguire l'override di una definizione non ereditata, CLI richiede l'uso della codifica precisa della dichiarazione originale.</span><span class="sxs-lookup"><span data-stu-id="ade0a-279">However, in order to override an inherited definition the CLI requires the precise encoding of the original declaration be used.</span></span> | <span data-ttu-id="ade0a-280">4</span><span class="sxs-lookup"><span data-stu-id="ade0a-280">4</span></span>
<span data-ttu-id="ade0a-281">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-281">Overloading</span></span> | [<span data-ttu-id="ade0a-282">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-282">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ade0a-283">Tutti i nomi introdotti in un ambito conforme a CLS devono essere di tipo indipendente e distinto, fatta eccezione per i casi in cui i nomi sono identici e vengono risolti tramite l'overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-283">All names introduced in a CLS-compliant scope shall be distinct independent of kind, except where the names are identical and resolved via overloading.</span></span> <span data-ttu-id="ade0a-284">Ad esempio, mentre CTS consente a un unico tipo di usare lo stesso nome per un metodo e per un campo, CLS non lo consente.</span><span class="sxs-lookup"><span data-stu-id="ade0a-284">That is, while the CTS allows a single type to use the same name for a method and a field, the CLS does not.</span></span> | <span data-ttu-id="ade0a-285">5</span><span class="sxs-lookup"><span data-stu-id="ade0a-285">5</span></span>
<span data-ttu-id="ade0a-286">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-286">Overloading</span></span> | [<span data-ttu-id="ade0a-287">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-287">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ade0a-288">I campi e i tipi annidati devono essere distinti in base al solo confronto tra identificatori, anche se CTS permette la distinzione di firme distinte.</span><span class="sxs-lookup"><span data-stu-id="ade0a-288">Fields and nested types shall be distinct by identifier comparison alone, even though the CTS allows distinct signatures to be distinguished.</span></span> <span data-ttu-id="ade0a-289">I metodi, le proprietà e gli eventi che hanno lo stesso nome (in base al confronto degli identificatori) dovranno presentare differenze più del solo tipo restituito, ad eccezione di quanto specificato nella regola CLS 39</span><span class="sxs-lookup"><span data-stu-id="ade0a-289">Methods, properties, and events that have the same name (by identifier comparison) shall differ by more than just the return type, except as specified in CLS Rule 39</span></span> | <span data-ttu-id="ade0a-290">6</span><span class="sxs-lookup"><span data-stu-id="ade0a-290">6</span></span>
<span data-ttu-id="ade0a-291">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-291">Overloading</span></span> | [<span data-ttu-id="ade0a-292">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-292">Overloads</span></span>](#overloads) | <span data-ttu-id="ade0a-293">È possibile eseguire l'overload solo di proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-293">Only properties and methods can be overloaded.</span></span> | <span data-ttu-id="ade0a-294">37</span><span class="sxs-lookup"><span data-stu-id="ade0a-294">37</span></span>
<span data-ttu-id="ade0a-295">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-295">Overloading</span></span> | [<span data-ttu-id="ade0a-296">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-296">Overloads</span></span>](#overloads) |<span data-ttu-id="ade0a-297">Le proprietà e i metodi possono essere sottoposti a overload solo in base al numero e ai tipi dei relativi parametri, a eccezione degli operatori di conversione denominati `op_Implicit` e `op_Explicit`, i quali possono essere anche sottoposti a overload in base al relativo tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-297">Properties and methods can be overloaded based only on the number and types of their parameters, except the conversion operators named `op_Implicit` and `op_Explicit`, which can also be overloaded based on their return type.</span></span> | <span data-ttu-id="ade0a-298">38</span><span class="sxs-lookup"><span data-stu-id="ade0a-298">38</span></span>
<span data-ttu-id="ade0a-299">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-299">Overloading</span></span> | -- | <span data-ttu-id="ade0a-300">Se due o più metodi conformi a CLS dichiarati in un tipo hanno lo stesso nome e, per un set specifico di creazioni di istanze del tipo, hanno lo stesso parametro e gli stesi tipi restituiti, tutti questi metodi saranno semanticamente equivalenti alle creazioni di istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-300">If two or more CLS-compliant methods declared in a type have the same name and, for a specific set of type instantiations, they have the same parameter and return types, then all these methods shall be semantically equivalent at those type instantiations.</span></span> | <span data-ttu-id="ade0a-301">48</span><span class="sxs-lookup"><span data-stu-id="ade0a-301">48</span></span>
<span data-ttu-id="ade0a-302">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-302">Properties</span></span> | [<span data-ttu-id="ade0a-303">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-303">Properties</span></span>](#properties) | <span data-ttu-id="ade0a-304">I metodi che implementano i metodi Get e Set di una proprietà devono essere contrassegnati come `SpecialName` nei metadati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-304">The methods that implement the getter and setter methods of a property shall be marked `SpecialName` in the metadata.</span></span> | <span data-ttu-id="ade0a-305">24</span><span class="sxs-lookup"><span data-stu-id="ade0a-305">24</span></span>
<span data-ttu-id="ade0a-306">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-306">Properties</span></span> | [<span data-ttu-id="ade0a-307">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-307">Properties</span></span>](#properties) | <span data-ttu-id="ade0a-308">Le funzioni di accesso di una proprietà devono essere tutte statiche, tutte virtuali o tutte istanze.</span><span class="sxs-lookup"><span data-stu-id="ade0a-308">A property's accessors shall all be static, all be virtual, or all be instance.</span></span> | <span data-ttu-id="ade0a-309">26</span><span class="sxs-lookup"><span data-stu-id="ade0a-309">26</span></span>
<span data-ttu-id="ade0a-310">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-310">Properties</span></span> | [<span data-ttu-id="ade0a-311">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-311">Properties</span></span>](#properties) | <span data-ttu-id="ade0a-312">Il tipo di una proprietà deve essere il tipo restituito del metodo Get e il tipo dell'ultimo argomento del metodo Set.</span><span class="sxs-lookup"><span data-stu-id="ade0a-312">The type of a property shall be the return type of the getter and the type of the last argument of the setter.</span></span> <span data-ttu-id="ade0a-313">I tipi dei parametri della proprietà devono essere i tipi dei parametri per il metodo Get e i tipi di tutti i parametri del metodo Set tranne l'ultimo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-313">The types of the parameters of the property shall be the types of the parameters to the getter and the types of all but the final parameter of the setter.</span></span> <span data-ttu-id="ade0a-314">Tutti questi tipi devono essere conformi a CLS e non devono essere puntatori gestiti, ossia non devono essere passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="ade0a-314">All of these types shall be CLS-compliant, and shall not be managed pointers (that is, shall not be passed by reference).</span></span> | <span data-ttu-id="ade0a-315">27</span><span class="sxs-lookup"><span data-stu-id="ade0a-315">27</span></span>
<span data-ttu-id="ade0a-316">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-316">Properties</span></span> | [<span data-ttu-id="ade0a-317">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-317">Properties</span></span>](#properties) | <span data-ttu-id="ade0a-318">Le proprietà devono essere conformi a un pattern di nome specifico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-318">Properties shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="ade0a-319">L'attributo `SpecialName` indicato nella regola CLS 24 deve essere ignorato nei confronti tra nomi appropriati e deve essere conforme alle regole dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-319">The `SpecialName` attribute referred to in CLS rule 24 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span> <span data-ttu-id="ade0a-320">Una proprietà deve disporre di un metodo Get, un metodo Set o di entrambi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-320">A property shall have a getter method, a setter method, or both.</span></span> | <span data-ttu-id="ade0a-321">28</span><span class="sxs-lookup"><span data-stu-id="ade0a-321">28</span></span>
<span data-ttu-id="ade0a-322">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-322">Type conversion</span></span> | [<span data-ttu-id="ade0a-323">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-323">Type conversion</span></span>](#type-conversion) | <span data-ttu-id="ade0a-324">Se viene specificato op_Implicit oppure op_Explicit, sarà necessario fornire un metodo alternativo di coercizione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-324">If either op_Implicit or op_Explicit is provided, an alternate means of providing the coercion shall be provided.</span></span> | <span data-ttu-id="ade0a-325">39</span><span class="sxs-lookup"><span data-stu-id="ade0a-325">39</span></span>
<span data-ttu-id="ade0a-326">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-326">Types</span></span> | [<span data-ttu-id="ade0a-327">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-327">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-328">I tipi di valore boxed non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-328">Boxed value types are not CLS-compliant.</span></span> | <span data-ttu-id="ade0a-329">3</span><span class="sxs-lookup"><span data-stu-id="ade0a-329">3</span></span>
<span data-ttu-id="ade0a-330">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-330">Types</span></span> | [<span data-ttu-id="ade0a-331">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-331">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-332">Tutti i tipi visualizzati in una firma devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-332">All types appearing in a signature shall be CLS-compliant.</span></span> <span data-ttu-id="ade0a-333">Tutti i tipi che costituiscono un tipo generico con istanze devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-333">All types composing an instantiated generic type shall be CLS-compliant.</span></span> | <span data-ttu-id="ade0a-334">11</span><span class="sxs-lookup"><span data-stu-id="ade0a-334">11</span></span>
<span data-ttu-id="ade0a-335">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-335">Types</span></span> | [<span data-ttu-id="ade0a-336">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-336">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-337">I riferimenti tipizzati non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-337">Typed references are not CLS-compliant.</span></span> | <span data-ttu-id="ade0a-338">14</span><span class="sxs-lookup"><span data-stu-id="ade0a-338">14</span></span>
<span data-ttu-id="ade0a-339">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-339">Types</span></span> | [<span data-ttu-id="ade0a-340">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-340">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-341">I tipi di puntatore non gestiti non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-341">Unmanaged pointer types are not CLS-compliant.</span></span> | <span data-ttu-id="ade0a-342">17</span><span class="sxs-lookup"><span data-stu-id="ade0a-342">17</span></span>
<span data-ttu-id="ade0a-343">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-343">Types</span></span> | [<span data-ttu-id="ade0a-344">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-344">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-345">Per le classi, i tipi di valore e le interfacce conformi a CLS non è necessaria l'implementazione di membri non conformi a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-345">CLS-compliant classes, value types, and interfaces shall not require the implementation of non-CLS-compliant members</span></span> | <span data-ttu-id="ade0a-346">20</span><span class="sxs-lookup"><span data-stu-id="ade0a-346">20</span></span>
<span data-ttu-id="ade0a-347">Tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-347">Types</span></span> | [<span data-ttu-id="ade0a-348">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-348">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ade0a-349">[System.Object](xref:System.Object) è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-349">[System.Object](xref:System.Object) is CLS-compliant.</span></span> <span data-ttu-id="ade0a-350">Qualsiasi altra classe conforme a CLS deve ereditare da una classe conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-350">Any other CLS-compliant class shall inherit from a CLS-compliant class.</span></span> | <span data-ttu-id="ade0a-351">23</span><span class="sxs-lookup"><span data-stu-id="ade0a-351">23</span></span>

<span data-ttu-id="ade0a-352">Indice delle sottosezioni:</span><span class="sxs-lookup"><span data-stu-id="ade0a-352">Index to subsections:</span></span>

* [<span data-ttu-id="ade0a-353">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-353">Types and type member signatures</span></span>](#types-and-type-member-signatures)
* [<span data-ttu-id="ade0a-354">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-354">Naming conventions</span></span>](#naming-conventions)
* [<span data-ttu-id="ade0a-355">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-355">Type conversion</span></span>](#type-conversion)
* [<span data-ttu-id="ade0a-356">Matrici</span><span class="sxs-lookup"><span data-stu-id="ade0a-356">Arrays</span></span>](#arrays)
* [<span data-ttu-id="ade0a-357">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-357">Interfaces</span></span>](#interfaces)
* [<span data-ttu-id="ade0a-358">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-358">Enumerations</span></span>](#enumerations)
* [<span data-ttu-id="ade0a-359">Membri dei tipi di in generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-359">Type members in general</span></span>](#type-members-in-general)
* [<span data-ttu-id="ade0a-360">Accessibilità del membro</span><span class="sxs-lookup"><span data-stu-id="ade0a-360">Member accessibility</span></span>](#member-accessibility)
* [<span data-ttu-id="ade0a-361">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-361">Generic types and members</span></span>](#generic-types-and-members)
* [<span data-ttu-id="ade0a-362">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-362">Constructors</span></span>](#constructors)
* [<span data-ttu-id="ade0a-363">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-363">Properties</span></span>](#properties)
* [<span data-ttu-id="ade0a-364">Events</span><span class="sxs-lookup"><span data-stu-id="ade0a-364">Events</span></span>](#events)
* [<span data-ttu-id="ade0a-365">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-365">Overloads</span></span>](#overloads)
* [<span data-ttu-id="ade0a-366">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-366">Exceptions</span></span>](#exceptions)
* [<span data-ttu-id="ade0a-367">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="ade0a-367">Attributes</span></span>](#attributes)

### <a name="types-and-type-member-signatures"></a><span data-ttu-id="ade0a-368">Tipi e firme dei membri di tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-368">Types and type member signatures</span></span>

<span data-ttu-id="ade0a-369">Il tipo [System.Object](xref:System.Object) è conforme a CLS ed è il tipo di base di tutti i tipi di oggetto nel sistema di tipo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ade0a-369">The [System.Object](xref:System.Object) type is CLS-compliant and is the base type of all object types in the .NET Framework type system.</span></span> <span data-ttu-id="ade0a-370">L'ereditarietà in .NET Framework è implicita (ad esempio la classe [String](xref:System.String) eredita in modo implicito dalla classe `Object`) o esplicita (ad esempio la classe [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) eredita in modo esplicito dalla classe [ArgumentException](xref:System.ArgumentException), che eredita in modo esplicito dalla classe [Exception](xref:System.Exception).</span><span class="sxs-lookup"><span data-stu-id="ade0a-370">Inheritance in the .NET Framework is either implicit (for example, the [String](xref:System.String) class implicitly inherits from the `Object` class) or explicit (for example, the [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) class explicitly inherits from the [ArgumentException](xref:System.ArgumentException) class, which explicitly inherits from the [Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="ade0a-371">Affinché un tipo derivato sia conforme a CLS, anche il tipo di base deve essere conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-371">For a derived type to be CLS compliant, its base type must also be CLS-compliant.</span></span>

<span data-ttu-id="ade0a-372">Nell'esempio seguente viene illustrato un tipo derivato il cui tipo di base non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-372">The following example shows a derived type whose base type is not CLS-compliant.</span></span> <span data-ttu-id="ade0a-373">Viene definita una classe `Counter` base tramite in cui viene usato un Unsigned Integer a 32 bit come contatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-373">It defines a base `Counter` class that uses an unsigned 32-bit integer as a counter.</span></span> <span data-ttu-id="ade0a-374">Poiché la classe fornisce la funzionalità contatore eseguendo il wrapping di un Unsigned Integer, la classe viene contrassegnata come non conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-374">Because the class provides counter functionality by wrapping an unsigned integer, the class is marked as non-CLS-compliant.</span></span> <span data-ttu-id="ade0a-375">Di conseguenza, anche una classe derivata, `NonZeroCounter`, non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-375">As a result, a derived class, `NonZeroCounter`, is also not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

<span data-ttu-id="ade0a-376">Tutti i tipi visualizzati nelle firme dei membri, incluso il tipo restituito di un metodo o un tipo di proprietà, devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-376">All types that appear in member signatures, including a method's return type or a property type, must be CLS-compliant.</span></span> <span data-ttu-id="ade0a-377">Inoltre, per i tipi generici:</span><span class="sxs-lookup"><span data-stu-id="ade0a-377">In addition, for generic types:</span></span>

* <span data-ttu-id="ade0a-378">Tutti i tipi che costituiscono un tipo generico con istanze devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-378">All types that compose an instantiated generic type must be CLS-compliant.</span></span>

* <span data-ttu-id="ade0a-379">Tutti i tipi usati come vincoli sui parametri generici devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-379">All types used as constraints on generic parameters must be CLS-compliant.</span></span>

<span data-ttu-id="ade0a-380">In [common type system](common-type-system.md) di .NET Framework è incluso un numero di tipi incorporati supportati direttamente da Common Language Runtime, codificati in particolare nei metadati di un assembly.</span><span class="sxs-lookup"><span data-stu-id="ade0a-380">The .NET [common type system](common-type-system.md) includes a number of built-in types that are supported directly by the common language runtime and are specially encoded in an assembly's metadata.</span></span> <span data-ttu-id="ade0a-381">Di questi tipi intrinseci, i tipi elencati nella tabella seguente sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-381">Of these intrinsic types, the types listed in the following table are CLS-compliant.</span></span>

<span data-ttu-id="ade0a-382">Tipo conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-382">CLS-compliant type</span></span> | <span data-ttu-id="ade0a-383">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade0a-383">Description</span></span>
------------------ | -----------
[<span data-ttu-id="ade0a-384">Byte</span><span class="sxs-lookup"><span data-stu-id="ade0a-384">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="ade0a-385">Unsigned Integer a 8 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-385">8-bit unsigned integer</span></span>
[<span data-ttu-id="ade0a-386">Int16</span><span class="sxs-lookup"><span data-stu-id="ade0a-386">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="ade0a-387">Signed Integer a 16 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-387">16-bit signed integer</span></span>
[<span data-ttu-id="ade0a-388">Int32</span><span class="sxs-lookup"><span data-stu-id="ade0a-388">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="ade0a-389">Intero con segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-389">32-bit signed integer</span></span>
[<span data-ttu-id="ade0a-390">Int64</span><span class="sxs-lookup"><span data-stu-id="ade0a-390">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="ade0a-391">Intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-391">64-bit signed integer</span></span>
[<span data-ttu-id="ade0a-392">Single</span><span class="sxs-lookup"><span data-stu-id="ade0a-392">Single</span></span>](xref:System.Single) | <span data-ttu-id="ade0a-393">Valore a virgola mobile e precisione singola</span><span class="sxs-lookup"><span data-stu-id="ade0a-393">Single-precision floating-point value</span></span>
[<span data-ttu-id="ade0a-394">Double</span><span class="sxs-lookup"><span data-stu-id="ade0a-394">Double</span></span>](xref:System.Double) | <span data-ttu-id="ade0a-395">Valore a virgola mobile a precisione doppia</span><span class="sxs-lookup"><span data-stu-id="ade0a-395">Double-precision floating-point value</span></span>
[<span data-ttu-id="ade0a-396">Boolean</span><span class="sxs-lookup"><span data-stu-id="ade0a-396">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="ade0a-397">tipo di valore true o false</span><span class="sxs-lookup"><span data-stu-id="ade0a-397">true or false value type</span></span>
[<span data-ttu-id="ade0a-398">Char</span><span class="sxs-lookup"><span data-stu-id="ade0a-398">Char</span></span>](xref:System.Char) | <span data-ttu-id="ade0a-399">Unità di codice codificata UTF-16</span><span class="sxs-lookup"><span data-stu-id="ade0a-399">UTF-16 encoded code unit</span></span>
[<span data-ttu-id="ade0a-400">Decimale</span><span class="sxs-lookup"><span data-stu-id="ade0a-400">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="ade0a-401">Numero decimale non a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="ade0a-401">Non-floating-point decimal number</span></span>
[<span data-ttu-id="ade0a-402">IntPtr</span><span class="sxs-lookup"><span data-stu-id="ade0a-402">IntPtr</span></span>](xref:System.IntPtr) | <span data-ttu-id="ade0a-403">Puntatore o handle di una dimensione definita dalla piattaforma</span><span class="sxs-lookup"><span data-stu-id="ade0a-403">Pointer or handle of a platform-defined size</span></span>
[<span data-ttu-id="ade0a-404">Stringa</span><span class="sxs-lookup"><span data-stu-id="ade0a-404">String</span></span>](xref:System.String) | <span data-ttu-id="ade0a-405">Raccolta di zero, uno o più oggetti Char</span><span class="sxs-lookup"><span data-stu-id="ade0a-405">Collection of zero, one, or more Char objects</span></span>

<span data-ttu-id="ade0a-406">I tipi intrinseci elencati nella tabella seguente non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-406">The intrinsic types listed in the following table are not CLS-Compliant.</span></span>

<span data-ttu-id="ade0a-407">Tipo non conforme</span><span class="sxs-lookup"><span data-stu-id="ade0a-407">Non-compliant type</span></span> | <span data-ttu-id="ade0a-408">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade0a-408">Description</span></span> | <span data-ttu-id="ade0a-409">Alternativa conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="ade0a-409">CLS-compliant alternative</span></span>
------------------ | ----------- | -------------------------
[<span data-ttu-id="ade0a-410">SByte</span><span class="sxs-lookup"><span data-stu-id="ade0a-410">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="ade0a-411">Tipo di dati Signed Integer a 8 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-411">8-bit signed integer data type</span></span> | [<span data-ttu-id="ade0a-412">Int16</span><span class="sxs-lookup"><span data-stu-id="ade0a-412">Int16</span></span>](xref:System.Int16)
[<span data-ttu-id="ade0a-413">UInt16</span><span class="sxs-lookup"><span data-stu-id="ade0a-413">UInt16</span></span>](xref:System.UInt16) | <span data-ttu-id="ade0a-414">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-414">16-bit unsigned integer</span></span> | [<span data-ttu-id="ade0a-415">Int32</span><span class="sxs-lookup"><span data-stu-id="ade0a-415">Int32</span></span>](xref:System.Int32)
[<span data-ttu-id="ade0a-416">UInt32</span><span class="sxs-lookup"><span data-stu-id="ade0a-416">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="ade0a-417">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-417">32-bit unsigned integer</span></span> | [<span data-ttu-id="ade0a-418">Int64</span><span class="sxs-lookup"><span data-stu-id="ade0a-418">Int64</span></span>](xref:System.Int64)
[<span data-ttu-id="ade0a-419">UInt64</span><span class="sxs-lookup"><span data-stu-id="ade0a-419">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="ade0a-420">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ade0a-420">64-bit unsigned integer</span></span> | <span data-ttu-id="ade0a-421">[Int64](xref:System.Int64) (possibile overflow), [BigInteger](xref:System.Numerics.BigInteger) o [Double](xref:System.Double)</span><span class="sxs-lookup"><span data-stu-id="ade0a-421">[Int64](xref:System.Int64) (may overflow), [BigInteger](xref:System.Numerics.BigInteger), or [Double](xref:System.Double)</span></span>
[<span data-ttu-id="ade0a-422">UIntPtr</span><span class="sxs-lookup"><span data-stu-id="ade0a-422">UIntPtr</span></span>](xref:System.UIntPtr) | <span data-ttu-id="ade0a-423">Puntatore o handle senza segno</span><span class="sxs-lookup"><span data-stu-id="ade0a-423">Unsigned pointer or handle</span></span> | [<span data-ttu-id="ade0a-424">IntPtr</span><span class="sxs-lookup"><span data-stu-id="ade0a-424">IntPtr</span></span>](xref:System.IntPtr)

<span data-ttu-id="ade0a-425">Nella libreria di classi .NET Framework o in qualsiasi altra libreria di classi possono essere inclusi altri tipi non conformi a CLS; ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ade0a-425">The .NET Framework Class Library or any other class library may include other types that aren't CLS-compliant; for example:</span></span>

* <span data-ttu-id="ade0a-426">Tipi di valore boxed.</span><span class="sxs-lookup"><span data-stu-id="ade0a-426">Boxed value types.</span></span> <span data-ttu-id="ade0a-427">Nell'esempio C# seguente viene creata una classe con una proprietà pubblica di tipo `int*` denominata `Value`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-427">The following C# example creates a class that has a public property of type `int*` named `Value`.</span></span> <span data-ttu-id="ade0a-428">Poiché `int*` è un tipo di valore boxed, viene contrassegnato come non conforme a CLS dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-428">Because an `int*` is a boxed value type, the compiler flags it as non-CLS-compliant.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* <span data-ttu-id="ade0a-429">Riferimenti tipizzati, che sono costrutti speciali contenenti un riferimento a un oggetto e un riferimento a un tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-429">Typed references, which are special constructs that contain a reference to an object and a reference to a type.</span></span>

<span data-ttu-id="ade0a-430">Se un tipo non è conforme a CLS, è necessario applicarvi l'attributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) con un parametro *isCompliant* con valore `false`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-430">If a type is not CLS-compliant, you should apply the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute with an *isCompliant* parameter with a value of `false` to it.</span></span> <span data-ttu-id="ade0a-431">Per altre informazioni, vedere la sezione [Attributo CLSCompliantAttribute](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="ade0a-431">For more information, see the [CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute) section.</span></span>

<span data-ttu-id="ade0a-432">Nell'esempio seguente viene illustrato il problema della conformità a CLS in una firma di metodo e nella creazione di un'istanza di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-432">The following example illustrates the problem of CLS compliance in a method signature and in generic type instantiation.</span></span> <span data-ttu-id="ade0a-433">Viene definita una classe `InvoiceItem` con una proprietà di tipo [UInt32](xref:System.UInt32), una proprietà di tipo [Nullable(Of UInt32)](xref:System.Nullable%601) e un costruttore con parametri di tipo `UInt32` e `Nullable(Of UInt32)`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-433">It defines an `InvoiceItem` class with a property of type [UInt32](xref:System.UInt32), a property of type [Nullable(Of UInt32)](xref:System.Nullable%601), and a constructor with parameters of type `UInt32` and `Nullable(Of UInt32)`.</span></span> <span data-ttu-id="ade0a-434">Vengono visualizzati quattro avvisi del compilatore quando si tenta di compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ade0a-434">You get four compiler warnings when you try to compile this example.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

<span data-ttu-id="ade0a-435">Per eliminare gli avvisi del compilatore, sostituire i tipi non conformi a CLS nell'interfaccia pubblica `InvoiceItem` con tipi conformi:</span><span class="sxs-lookup"><span data-stu-id="ade0a-435">To eliminate the compiler warnings, replace the non-CLS-compliant types in the `InvoiceItem` public interface with compliant types:</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

<span data-ttu-id="ade0a-436">Oltre ai tipi specifici elencati, alcune categorie di tipi non sono conformi a CLS,</span><span class="sxs-lookup"><span data-stu-id="ade0a-436">In addition to the specific types listed, some categories of types are not CLS compliant.</span></span> <span data-ttu-id="ade0a-437">tra cui, tipi di puntatore non gestiti e tipi di puntatore a funzione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-437">These include unmanaged pointer types and function pointer types.</span></span> <span data-ttu-id="ade0a-438">Nell'esempio seguente viene generato un avviso del compilatore perché viene usato un puntatore a un Integer per creare una matrice di Integer.</span><span class="sxs-lookup"><span data-stu-id="ade0a-438">The following example generates a compiler warning because it uses a pointer to an integer to create an array of integers.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

<span data-ttu-id="ade0a-439">Per le classi astratte conformi a CLS (cioè quelle contrassegnate come `abstract` in C#), anche tutti i membri della classe devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-439">For CLS-compliant abstract classes (that is, classes marked as `abstract` in C#), all members of the class must also be CLS-compliant.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="ade0a-440">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="ade0a-440">Naming conventions</span></span>

<span data-ttu-id="ade0a-441">Poiché per alcuni linguaggi di programmazione non viene fatta distinzione tra maiuscole e minuscole, gli identificatori, ad esempio i nomi degli spazi dei nomi, i tipi e i membri, occorre che non differiscano solo per la combinazione di caratteri maiuscoli o minuscoli.</span><span class="sxs-lookup"><span data-stu-id="ade0a-441">Because some programming languages are case-insensitive, identifiers (such as the names of namespaces, types, and members) must differ by more than case.</span></span> <span data-ttu-id="ade0a-442">Due identificatori sono considerati equivalenti se i relativi mapping di minuscole sono uguali.</span><span class="sxs-lookup"><span data-stu-id="ade0a-442">Two identifiers are considered equivalent if their lowercase mappings are the same.</span></span> <span data-ttu-id="ade0a-443">Nell'esempio di C# seguente vengono definite due classi pubbliche, `Person` e `person`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-443">The following C# example defines two public classes, `Person` and `person`.</span></span> <span data-ttu-id="ade0a-444">Poiché si differenziano solo per le maiuscole e le minuscole, dal compilatore C# vengono contrassegnate come non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-444">Because they differ only by case, the C# compiler flags them as not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

<span data-ttu-id="ade0a-445">Gli identificatori del linguaggio di programmazione, ad esempio i nomi degli spazi dei nomi, i tipi e i membri, devono essere conformi allo [standard Unicode](https://unicode.org/reports/tr15/).</span><span class="sxs-lookup"><span data-stu-id="ade0a-445">Programming language identifiers, such as the names of namespaces, types, and members, must conform to the [Unicode Standard](https://unicode.org/reports/tr15/).</span></span> <span data-ttu-id="ade0a-446">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="ade0a-446">This means that:</span></span>

* <span data-ttu-id="ade0a-447">Il primo carattere di un identificatore può essere qualsiasi carattere Unicode, una lettera maiuscola, una lettera minuscola, tutte iniziali maiuscole, una lettera di modificatore, un'altra lettera o un numero rappresentato dalla lettera.</span><span class="sxs-lookup"><span data-stu-id="ade0a-447">The first character of an identifier can be any Unicode uppercase letter, lowercase letter, title case letter, modifier letter, other letter, or letter number.</span></span> <span data-ttu-id="ade0a-448">Per informazioni sulle categorie di caratteri Unicode, vedere l'enumerazione [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory).</span><span class="sxs-lookup"><span data-stu-id="ade0a-448">For information on Unicode character categories, see the [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory) enumeration.</span></span>

* <span data-ttu-id="ade0a-449">I caratteri successivi possono provenire da una qualsiasi delle categorie come primo carattere e possono includere anche segni di non spaziatura, contrassegni di combinazione di spaziatura, numeri decimali, punteggiatura del connettore e codici di formattazione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-449">Subsequent characters can be from any of the categories as the first character, and can also include non-spacing marks, spacing combining marks, decimal numbers, connector punctuation, and formatting codes.</span></span>

<span data-ttu-id="ade0a-450">Prima di confrontare gli identificatori, è necessario filtrare i codici di formattazione e convertire gli identificatori nel formato di normalizzazione Unicode C, poiché un singolo carattere può essere rappresentato da più unità di codice codificate UTF-16.</span><span class="sxs-lookup"><span data-stu-id="ade0a-450">Before you compare identifiers, you should filter out formatting codes and convert the identifiers to Unicode Normalization Form C, because a single character can be represented by multiple UTF-16-encoded code units.</span></span> <span data-ttu-id="ade0a-451">Le sequenze di caratteri che producono le stesse unità di codice nel formato di normalizzazione Unicode C non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-451">Character sequences that produce the same code units in Unicode Normalization Form C are not CLS-compliant.</span></span> <span data-ttu-id="ade0a-452">L'esempio seguente definisce una proprietà denominata `Å`, costituita dal carattere SEGNO di ANGSTROM (U+212B) e una seconda proprietà denominata `Å`, costituita dal carattere LETTERA LATINA A MAIUSCOLA CON UN CERCHIO SOPRA (U+00C5).</span><span class="sxs-lookup"><span data-stu-id="ade0a-452">The following example defines a property named `Å`, which consists of the character ANGSTROM SIGN (U+212B), and a second property named `Å`, which consists of the character LATIN CAPITAL LETTER A WITH RING ABOVE (U+00C5).</span></span> <span data-ttu-id="ade0a-453">Il compilatore C# contrassegna il codice sorgente come non conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-453">The C# compiler flags the source code as non-CLS-compliant.</span></span>

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

<span data-ttu-id="ade0a-454">I nomi dei membri all'interno di un ambito specifico (ad esempio gli spazi dei nomi in un assembly, i tipi in uno spazio dei nomi o i membri in un tipo) devono essere univoci ad eccezione dei nomi che vengono risolti tramite l'overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-454">Member names within a particular scope (such as the namespaces within an assembly, the types within a namespace, or the members within a type) must be unique except for names that are resolved through overloading.</span></span> <span data-ttu-id="ade0a-455">Questo requisito è più rigido di quello di Common Type System, che consente a più membri all'interno di un ambito di disporre di nomi identici purché siano tipi diversi di membri (ad esempio, uno è un metodo e uno è un campo).</span><span class="sxs-lookup"><span data-stu-id="ade0a-455">This requirement is more stringent than that of the common type system, which allows multiple members within a scope to have identical names as long as they are different kinds of members (for example, one is a method and one is a field).</span></span> <span data-ttu-id="ade0a-456">In particolare, per i membri di tipo:</span><span class="sxs-lookup"><span data-stu-id="ade0a-456">In particular, for type members:</span></span>

* <span data-ttu-id="ade0a-457">I campi e i tipi annidati vengono distinti solo in base al nome.</span><span class="sxs-lookup"><span data-stu-id="ade0a-457">Fields and nested types are distinguished by name alone.</span></span>

* <span data-ttu-id="ade0a-458">I metodi, le proprietà e gli eventi che hanno lo stesso nome devono presentare differenze che vanno oltre il solo tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-458">Methods, properties, and events that have the same name must differ by more than just return type.</span></span>

<span data-ttu-id="ade0a-459">Nell'esempio seguente viene illustrato il requisito in base al quale i nomi dei membri devono essere univoci all'interno del relativo ambito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-459">The following example illustrates the requirement that member names must be unique within their scope.</span></span> <span data-ttu-id="ade0a-460">Viene definita una classe denominata `Converter` in cui sono inclusi quattro membri denominati `Conversion`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-460">It defines a class named `Converter` that includes four members named `Conversion`.</span></span> <span data-ttu-id="ade0a-461">Tre sono metodi e uno è una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ade0a-461">Three are methods, and one is a property.</span></span> <span data-ttu-id="ade0a-462">Il metodo che prevede un parametro `Int64` è denominato in modo univoco, ma i due metodi con un parametro `Int32` non lo sono, poiché il valore restituito non è considerato parte della firma di un membro.</span><span class="sxs-lookup"><span data-stu-id="ade0a-462">The method that includes an `Int64` parameter is uniquely named, but the two methods with an `Int32` parameter are not, because return value is not considered a part of a member's signature.</span></span> <span data-ttu-id="ade0a-463">Questo requisito viene violato anche dalla proprietà `Conversion`, poiché le proprietà non possono disporre dello stesso nome dei metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-463">The `Conversion` property also violates this requirement, because properties cannot have the same name as overloaded methods.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

<span data-ttu-id="ade0a-464">Nei singoli linguaggi sono incluse parole chiave univoche, pertanto i linguaggi destinati a Common Language Runtime devono fornire anche un meccanismo di riferimento agli identificatori (ad esempio nomi di tipi) che coincidono con le parole chiave.</span><span class="sxs-lookup"><span data-stu-id="ade0a-464">Individual languages include unique keywords, so languages that target the common language runtime must also provide some mechanism for referencing identifiers (such as type names) that coincide with keywords.</span></span> <span data-ttu-id="ade0a-465">Ad esempio, `case` è una parola chiave sia in C# sia in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ade0a-465">For example, `case` is a keyword in both C# and Visual Basic.</span></span> <span data-ttu-id="ade0a-466">Tuttavia, nell'esempio di Visual Basic seguente è possibile evitare ambiguità relative a una classe denominata `case` dalla parola chiave `case` usando le parentesi graffe di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="ade0a-466">However, the following Visual Basic example is able to disambiguate a class named `case` from the `case` keyword by using opening and closing braces.</span></span> <span data-ttu-id="ade0a-467">In caso contrario, nell'esempio verrà generato il messaggio di errore "Parola chiave non valida come identificatore" e la compilazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="ade0a-467">Otherwise, the example would produce the error message, "Keyword is not valid as an identifier," and fail to compile.</span></span>

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

<span data-ttu-id="ade0a-468">Nell'esempio C# seguente viene creata un'istanza della classe `case` usando il simbolo @ per distinguere l'identificatore dalla parola chiave del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ade0a-468">The following C# example is able to instantiate the `case` class by using the @ symbol to disambiguate the identifier from the language keyword.</span></span> <span data-ttu-id="ade0a-469">Senza, tramite il compilatore C# verrebbero visualizzati due messaggi di errore, "È previsto un tipo" e "'case' è un termine non valido nell'espressione".</span><span class="sxs-lookup"><span data-stu-id="ade0a-469">Without it, the C# compiler would display two error messages, "Type expected" and "Invalid expression term 'case'."</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a><span data-ttu-id="ade0a-470">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ade0a-470">Type conversion</span></span>

<span data-ttu-id="ade0a-471">Tramite le specifiche CLS (Common Language Specification) vengono definiti due operatori di conversione:</span><span class="sxs-lookup"><span data-stu-id="ade0a-471">The Common Language Specification defines two conversion operators:</span></span>

* <span data-ttu-id="ade0a-472">`op_Implicit`, che viene usato per le conversioni verso un tipo di dati più grande che non comportano la perdita di dati o di precisione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-472">`op_Implicit`, which is used for widening conversions that do not result in loss of data or precision.</span></span> <span data-ttu-id="ade0a-473">Ad esempio, nella struttura [Decimal](xref:System.Decimal) è incluso un operatore `op_Implicit` di overload per convertire i valori di tipi integrali e i valori [Char](xref:System.Char) in valori `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-473">For example, the [Decimal](xref:System.Decimal) structure includes an overloaded `op_Implicit` operator to convert values of integral types and [Char](xref:System.Char) values to `Decimal` values.</span></span>

* <span data-ttu-id="ade0a-474">`op_Explicit`, che viene usato per le conversioni verso un tipo di dati più piccolo che possono comportare la perdita di grandezza (un valore viene convertito in un altro a cui è associato un intervallo inferiore) o di precisione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-474">`op_Explicit`, which is used for narrowing conversions that can result in loss of magnitude (a value is converted to a value that has a smaller range) or precision.</span></span> <span data-ttu-id="ade0a-475">Ad esempio, nella struttura `Decimal` è incluso un operatore `op_Explicit` di overload per convertire i valori [Double](xref:System.Double) e [Single](xref:System.Single) in `Decimal` e per convertire i valori `Decimal` in valori integrali `Double`, `Single` e `Char`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-475">For example, the `Decimal` structure includes an overloaded `op_Explicit` operator to convert [Double](xref:System.Double) and [Single](xref:System.Single) values to `Decimal` and to convert `Decimal` values to integral values, `Double`, `Single`, and `Char`.</span></span>

<span data-ttu-id="ade0a-476">Tuttavia, non tutti i linguaggi supportano l'overload degli operatori o la definizione di operatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-476">However, not all languages support operator overloading or the definition of custom operators.</span></span> <span data-ttu-id="ade0a-477">Se si sceglie di implementare questi operatori di conversione, è necessario fornire anche un modo alternativo per eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-477">If you choose to implement these conversion operators, you should also provide an alternate way to perform the conversion.</span></span> <span data-ttu-id="ade0a-478">È consigliabile fornire i metodi `From`Xxx e `To`Xxx.</span><span class="sxs-lookup"><span data-stu-id="ade0a-478">We recommend that you provide `From`Xxx and `To`Xxx methods.</span></span>

<span data-ttu-id="ade0a-479">Nell'esempio seguente vengono definite le convenzioni esplicite e implicite conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-479">The following example defines CLS-compliant implicit and explicit conversions.</span></span> <span data-ttu-id="ade0a-480">Viene creata una `UDouble` classe che rappresenta un numero a virgola mobile e precisione doppia con segno.</span><span class="sxs-lookup"><span data-stu-id="ade0a-480">It creates a `UDouble` class that represents a signed double-precision, floating-point number.</span></span> <span data-ttu-id="ade0a-481">Viene usato per le conversioni implicite da `UDouble` a `Double` e per le conversioni esplicite da `UDouble` a `Single`, da `Double` a `UDouble` e da `Single` a `UDouble`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-481">It provides for implicit conversions from `UDouble` to `Double` and for explicit conversions from `UDouble` to `Single`, `Double` to `UDouble`, and `Single` to `UDouble`.</span></span> <span data-ttu-id="ade0a-482">Vengono anche definiti un metodo `ToDouble` come alternativa all'operatore di conversione implicito e i metodi `ToSingle`, `FromDouble` e `FromSingle` come alternative agli operatori di conversione espliciti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-482">It also defines a `ToDouble` method as an alternative to the implicit conversion operator and the `ToSingle`, `FromDouble`, and `FromSingle` methods as alternatives to the explicit conversion operators.</span></span>

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a><span data-ttu-id="ade0a-483">Matrici</span><span class="sxs-lookup"><span data-stu-id="ade0a-483">Arrays</span></span>

<span data-ttu-id="ade0a-484">Le matrici conformi a CLS sono conformi alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="ade0a-484">CLS-compliant arrays conform to the following rules:</span></span>

* <span data-ttu-id="ade0a-485">Il limite inferiore di tutte le dimensioni di una matrice deve essere uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="ade0a-485">All dimensions of an array must have a lower bound of zero.</span></span> <span data-ttu-id="ade0a-486">Nell'esempio seguente viene creata una matrice non conforme a CLS con un limite inferiore pari a uno.</span><span class="sxs-lookup"><span data-stu-id="ade0a-486">The following example creates a non-CLS-compliant array with a lower bound of one.</span></span> <span data-ttu-id="ade0a-487">Nonostante la presenza dell'attributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) , il compilatore non rileva che la matrice restituita dal `Numbers.GetTenPrimes` metodo non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-487">Despite the presence of the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute, the compiler does not detect that the array returned by the `Numbers.GetTenPrimes` method is not CLS-compliant.</span></span>

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* <span data-ttu-id="ade0a-488">Tutti gli elementi delle matrici devono essere costituiti da tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-488">All array elements must consist of CLS-compliant types.</span></span> <span data-ttu-id="ade0a-489">Nell'esempio seguente vengono definiti due metodi tramite cui vengono restituite matrici non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-489">The following example defines two methods that return non-CLS-compliant arrays.</span></span> <span data-ttu-id="ade0a-490">Il primo restituisce una matrice di valori [UInt32](xref:System.UInt32).</span><span class="sxs-lookup"><span data-stu-id="ade0a-490">The first returns an array of [UInt32](xref:System.UInt32) values.</span></span> <span data-ttu-id="ade0a-491">Il secondo restituisce una matrice [Object](xref:System.Object) che include valori [Int32](xref:System.Int32) e `UInt32`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-491">The second returns an [Object](xref:System.Object) array that includes [Int32](xref:System.Int32) and `UInt32` values.</span></span> <span data-ttu-id="ade0a-492">Anche se il compilatore consente di identificare la prima matrice come non conforme a causa del relativo tipo `UInt32`, non è in grado di riconoscere che nella seconda matrice sono inclusi elementi non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-492">Although the compiler identifies the first array as non-compliant because of its `UInt32` type, it fails to recognize that the second array includes non-CLS-compliant elements.</span></span>

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* <span data-ttu-id="ade0a-493">La risoluzione dell'overload per i metodi a cui sono associati parametri di matrice è basata sul fatto che si tratta di matrici e sul relativo tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="ade0a-493">Overload resolution for methods that have array parameters is based on the fact that they are arrays and on their element type.</span></span> <span data-ttu-id="ade0a-494">Per questo motivo, la seguente definizione di un metodo `GetSquares` di overload è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-494">For this reason, the following definition of an overloaded `GetSquares` method is CLS-compliant.</span></span>

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a><span data-ttu-id="ade0a-495">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ade0a-495">Interfaces</span></span>

<span data-ttu-id="ade0a-496">Tramite interfacce conformi a CLS è possibile definire proprietà, eventi e metodi virtuali (metodi senza l'implementazione).</span><span class="sxs-lookup"><span data-stu-id="ade0a-496">CLS-compliant interfaces can define properties, events, and virtual methods (methods with no implementation).</span></span> <span data-ttu-id="ade0a-497">Un'interfaccia conforme a CLS non può disporre di uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ade0a-497">A CLS-compliant interface cannot have any of the following:</span></span>

* <span data-ttu-id="ade0a-498">Metodi o campi statici.</span><span class="sxs-lookup"><span data-stu-id="ade0a-498">Static methods or static fields.</span></span> <span data-ttu-id="ade0a-499">Se si definisce un membro statico in un'interfaccia, il compilatore C# genera errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-499">The C# compiler generates compiler errors if you define a static member in an interface.</span></span>

* <span data-ttu-id="ade0a-500">Campi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-500">Fields.</span></span> <span data-ttu-id="ade0a-501">Se si definisce un campo in un'interfaccia, il compilatore C# genera errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-501">The C# a compiler generates compiler errors if you define a field in an interface.</span></span>

* <span data-ttu-id="ade0a-502">Metodi non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-502">Methods that are not CLS-compliant.</span></span> <span data-ttu-id="ade0a-503">Ad esempio, nella definizione dell'interfaccia seguente è incluso un metodo, `INumber.GetUnsigned`, che è contrassegnato come non conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-503">For example, the following interface definition includes a method, `INumber.GetUnsigned`, that is marked as non-CLS-compliant.</span></span> <span data-ttu-id="ade0a-504">In questo esempio verrà generato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-504">This example generates a compiler warning.</span></span>

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  <span data-ttu-id="ade0a-505">A causa di questa regola, i tipi conformi a CLS non sono necessari per l'implementazione di membri non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-505">Because of this rule, CLS-compliant types are not required to implement non-CLS-compliant members.</span></span> <span data-ttu-id="ade0a-506">Se tramite un framework conforme a CLS viene esposta una classe mediante la quale viene implementata un'interfaccia non conforme a CLS, è anche consigliabile fornire implementazioni concrete di tutti i membri non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-506">If a CLS-compliant framework does expose a class that implements a non-CLS compliant interface, it should also provide concrete implementations of all non-CLS-compliant members.</span></span>

<span data-ttu-id="ade0a-507">I compilatori di linguaggi conformi a CLS devono anche consentire a una classe di fornire implementazioni separate di membri con lo stesso nome e la stessa firma in più interfacce.</span><span class="sxs-lookup"><span data-stu-id="ade0a-507">CLS-compliant language compilers must also allow a class to provide separate implementations of members that have the same name and signature in multiple interfaces.</span></span> <span data-ttu-id="ade0a-508">C# supporta implementazioni di interfacce esplicite per fornire diverse implementazioni di metodi denominati in modo identico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-508">C# supports explicit interface implementations to provide different implementations of identically named methods.</span></span> <span data-ttu-id="ade0a-509">Nell'esempio seguente viene illustrato questo scenario definendo una classe `Temperature` mediante la quale vengono implementate le interfacce `ICelsius` e `IFahrenheit` come implementazioni di interfacce esplicite.</span><span class="sxs-lookup"><span data-stu-id="ade0a-509">The following example illustrates this scenario by defining a `Temperature` class that implements the `ICelsius` and `IFahrenheit` interfaces as explicit interface implementations.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a><span data-ttu-id="ade0a-510">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-510">Enumerations</span></span>

<span data-ttu-id="ade0a-511">Le enumerazioni conformi a CLS devono rispettare queste regole:</span><span class="sxs-lookup"><span data-stu-id="ade0a-511">CLS-compliant enumerations must follow these rules:</span></span>

* <span data-ttu-id="ade0a-512">Il tipo sottostante dell'enumerazione deve essere un Integer intrinseco conforme a CLS ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) o [Int64](xref:System.Int64)).</span><span class="sxs-lookup"><span data-stu-id="ade0a-512">The underlying type of the enumeration must be an intrinsic CLS-compliant integer ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), or [Int64](xref:System.Int64)).</span></span> <span data-ttu-id="ade0a-513">Ad esempio, il codice seguente tenta di definire un'enumerazione il cui tipo sottostante è [UInt32](xref:System.UInt32) e genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-513">For example, the following code tries to define an enumeration whose underlying type is [UInt32](xref:System.UInt32) and generates a compiler warning.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* <span data-ttu-id="ade0a-514">Un tipo di enumerazione deve avere un singolo campo di istanza denominato `Value__` contrassegnato con l'attributo `FieldAttributes.RTSpecialName`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-514">An enumeration type must have a single instance field named `Value__` that is marked with the `FieldAttributes.RTSpecialName` attribute.</span></span> <span data-ttu-id="ade0a-515">Ciò consente di fare riferimento al valore del campo in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-515">This enables you to reference the field value implicitly.</span></span>

* <span data-ttu-id="ade0a-516">Un'enumerazione prevede campi statici con valori letterali i cui tipi corrispondono al tipo dell'enumerazione stessa.</span><span class="sxs-lookup"><span data-stu-id="ade0a-516">An enumeration includes literal static fields whose types match the type of the enumeration itself.</span></span> <span data-ttu-id="ade0a-517">Ad esempio, se si definisce un'enumerazione `State` con valori `State.On` e `State.Off`, `State.On` e `State.Off` sono entrambi campi statici con valori letterali il cui tipo è `State`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-517">For example, if you define a `State` enumeration with values of `State.On` and `State.Off`, `State.On` and `State.Off` are both literal static fields whose type is `State`.</span></span>

* <span data-ttu-id="ade0a-518">Vi sono due tipi di enumerazioni:</span><span class="sxs-lookup"><span data-stu-id="ade0a-518">There are two kinds of enumerations:</span></span>

  * <span data-ttu-id="ade0a-519">Enumerazione che rappresenta un set di Integer denominati che si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="ade0a-519">An enumeration that represents a set of mutually exclusive, named integer values.</span></span> <span data-ttu-id="ade0a-520">Questo tipo di enumerazione è indicato dall'assenza dell'attributo personalizzato [System.FlagsAttribute](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="ade0a-520">This type of enumeration is indicated by the absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

  * <span data-ttu-id="ade0a-521">Enumerazione che rappresenta un set di flag di bit che possono essere combinati per generare un valore senza nome.</span><span class="sxs-lookup"><span data-stu-id="ade0a-521">An enumeration that represents a set of bit flags that can combine to generate an unnamed value.</span></span> <span data-ttu-id="ade0a-522">Questo tipo di enumerazione è indicato dalla presenza dell'attributo personalizzato [System.FlagsAttribute](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="ade0a-522">This type of enumeration is indicated by the presence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

<span data-ttu-id="ade0a-523">Per altre informazioni, vedere la documentazione relativa alla struttura [Enum](xref:System.Enum).</span><span class="sxs-lookup"><span data-stu-id="ade0a-523">For more information, see the documentation for the [Enum](xref:System.Enum) structure.</span></span>

* <span data-ttu-id="ade0a-524">Il valore di un'enumerazione non è limitato all'intervallo dei relativi valori specificati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-524">The value of an enumeration is not limited to the range of its specified values.</span></span> <span data-ttu-id="ade0a-525">In altre parole, l'intervallo di valori in una enumerazione è l'intervallo del relativo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="ade0a-525">In other words, the range of values in an enumeration is the range of its underlying value.</span></span> <span data-ttu-id="ade0a-526">È possibile usare il metodo `Enum.IsDefined` per determinare se un valore specificato è un membro di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-526">You can use the `Enum.IsDefined` method to determine whether a specified value is a member of an enumeration.</span></span>

### <a name="type-members-in-general"></a><span data-ttu-id="ade0a-527">Membri dei tipi in generale</span><span class="sxs-lookup"><span data-stu-id="ade0a-527">Type members in general</span></span>

<span data-ttu-id="ade0a-528">In base alle specifiche CLS (Common Language Specification), l'accesso a tutti i campi e metodi deve essere effettuato come membri di una classe particolare.</span><span class="sxs-lookup"><span data-stu-id="ade0a-528">The Common Language Specification requires all fields and methods to be accessed as members of a particular class.</span></span> <span data-ttu-id="ade0a-529">Pertanto, i campi e i metodi statici globali, vale a dire campi o metodi statici definiti oltre a un tipo, non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-529">Therefore, global static fields and methods (that is, static fields or methods that are defined apart from a type) are not CLS-compliant.</span></span> <span data-ttu-id="ade0a-530">Se si tenta di includere un campo o un metodo globale nel codice sorgente, il compilatore C# genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-530">If you try to include a global field or method in your source code, the C# compiler generates a compiler error.</span></span>

<span data-ttu-id="ade0a-531">Le specifiche CLS (Common Language Specification) supportano solo la convenzione di chiamata gestita standard.</span><span class="sxs-lookup"><span data-stu-id="ade0a-531">The Common Language Specification supports only the standard managed calling convention.</span></span> <span data-ttu-id="ade0a-532">Non supportano le convenzioni di chiamata non gestite né i metodi con elenchi di argomenti variabili contrassegnati con la parola chiave `varargs`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-532">It doesn't support unmanaged calling conventions and methods with variable argument lists marked with the `varargs` keyword.</span></span> <span data-ttu-id="ade0a-533">Per gli elenchi di argomenti variabili compatibili con la convenzione di chiamata gestita standard, usare l'attributo [ParamArrayAttribute](xref:System.ParamArrayAttribute) o l'implementazione del singolo linguaggio, ad esempio la parola chiave `params` in C# e la parola chiave `ParamArray` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ade0a-533">For variable argument lists that are compatible with the standard managed calling convention, use the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute or the individual language's implementation, such as the `params` keyword in C# and the `ParamArray` keyword in Visual Basic.</span></span>

### <a name="member-accessibility"></a><span data-ttu-id="ade0a-534">Accessibilità del membro</span><span class="sxs-lookup"><span data-stu-id="ade0a-534">Member accessibility</span></span>

<span data-ttu-id="ade0a-535">Tramite l'override di un membro ereditato non è possibile modificare l'accessibilità del membro in questione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-535">Overriding an inherited member cannot change the accessibility of that member.</span></span> <span data-ttu-id="ade0a-536">Ad esempio, un metodo pubblico in una classe di base non può essere sottoposto a override da un metodo privato in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ade0a-536">For example, a public method in a base class cannot be overridden by a private method in a derived class.</span></span> <span data-ttu-id="ade0a-537">Vi è un'eccezione: un membro `protected internal` (in C#) o `Protected Friend` (in Visual Basic) in un assembly sottoposto a override da un tipo in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-537">There is one exception: a `protected internal` (in C#) or `Protected Friend` (in Visual Basic) member in one assembly that is overridden by a type in a different assembly.</span></span>  <span data-ttu-id="ade0a-538">In questo caso, l'accessibilità dell'override è `Protected`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-538">In that case, the accessibility of the override is `Protected`.</span></span>

<span data-ttu-id="ade0a-539">L'esempio seguente mostra l'errore generato quando l'attributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) è impostato su `true` e `Person`, cioè una classe derivata da `Animal`, tenta di modificare l'accessibilità della proprietà `Species` da pubblica a privata.</span><span class="sxs-lookup"><span data-stu-id="ade0a-539">The following example illustrates the error that is generated when the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is set to `true`, and `Person`, which is a class derived from `Animal`, tries to change the accessibility of the `Species` property from public to private.</span></span> <span data-ttu-id="ade0a-540">L'esempio viene compilato correttamente se la relativa accessibilità è stata modificata in pubblica.</span><span class="sxs-lookup"><span data-stu-id="ade0a-540">The example compiles successfully if its accessibility is changed to public.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

<span data-ttu-id="ade0a-541">I tipi nella firma di un membro devono essere accessibili ogni volta che il membro è accessibile.</span><span class="sxs-lookup"><span data-stu-id="ade0a-541">Types in the signature of a member must be accessible whenever that member is accessible.</span></span> <span data-ttu-id="ade0a-542">Questo significa, ad esempio, che un membro pubblico non può includere un parametro il cui tipo è privato, protetto o interno.</span><span class="sxs-lookup"><span data-stu-id="ade0a-542">For example, this means that a public member cannot include a parameter whose type is private, protected, or internal.</span></span> <span data-ttu-id="ade0a-543">Nell'esempio seguente viene illustrato l'errore del compilatore generato quando tramite un costruttore di classe `StringWrapper` viene esposto un valore di enumerazione `StringOperationType` interno con cui si determina la modalità di esecuzione del wrapping di un valore stringa.</span><span class="sxs-lookup"><span data-stu-id="ade0a-543">The following example illustrates the compiler error that results when a `StringWrapper` class constructor exposes an internal `StringOperationType` enumeration value that determines how a string value should be wrapped.</span></span>

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a><span data-ttu-id="ade0a-544">Tipi e membri generici</span><span class="sxs-lookup"><span data-stu-id="ade0a-544">Generic types and members</span></span>

<span data-ttu-id="ade0a-545">I tipi annidati dispongono sempre di un numero di parametri generici almeno pari a quelli del relativo tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-545">Nested types always have at least as many generic parameters as their enclosing type.</span></span> <span data-ttu-id="ade0a-546">Questi corrispondono per posizione ai parametri generici del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ade0a-546">These correspond by position to the generic parameters in the enclosing type.</span></span> <span data-ttu-id="ade0a-547">Il tipo generico può anche prevedere nuovi parametri generici.</span><span class="sxs-lookup"><span data-stu-id="ade0a-547">The generic type can also include new generic parameters.</span></span>

<span data-ttu-id="ade0a-548">La relazione tra i parametri di tipo generico di un tipo contenitore e i relativi tipi annidati può essere nascosta dalla sintassi dei singoli linguaggi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-548">The relationship between the generic type parameters of a containing type and its nested types may be hidden by the syntax of individual languages.</span></span> <span data-ttu-id="ade0a-549">Nell'esempio seguente in un tipo generico `Outer<T>` sono contenute due classi annidate, `Inner1A` e `Inner1B<U>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-549">In the following example, a generic type `Outer<T>` contains two nested classes, `Inner1A` and `Inner1B<U>`.</span></span> <span data-ttu-id="ade0a-550">Le chiamate al metodo `ToString`, che ogni classe eredita da `Object.ToString`, mostrano che in ogni classe annidata sono inclusi i parametri di tipo della relativa classe che li contiene.</span><span class="sxs-lookup"><span data-stu-id="ade0a-550">The calls to the `ToString` method, which each class inherits from `Object.ToString`, show that each nested class includes the type parameters of its containing class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

<span data-ttu-id="ade0a-551">I nomi di tipo generico sono codificati nel formato *name*'*n*, dove *name* è il nome del tipo, *\`* è un valore letterale del carattere e *n* è il numero di parametri dichiarati nel tipo oppure, per i tipi generici annidati, il numero di parametri di tipo appena introdotti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-551">Generic type names are encoded in the form *name*'*n*, where *name* is the type name, *\`* is a character literal, and *n* is the number of parameters declared on the type, or, for nested generic types, the number of newly introduced type parameters.</span></span> <span data-ttu-id="ade0a-552">Questa codifica dei nomi di tipo generico è principalmente di interesse per gli sviluppatori che usano la reflection per accedere ai tipi generici conformi a CLS in una libreria.</span><span class="sxs-lookup"><span data-stu-id="ade0a-552">This encoding of generic type names is primarily of interest to developers who use reflection to access CLS-complaint generic types in a library.</span></span>

<span data-ttu-id="ade0a-553">Se i vincoli vengono applicati a un tipo generico, anche tutti i tipi usati come vincoli devono essere conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-553">If constraints are applied to a generic type, any types used as constraints must also be CLS-compliant.</span></span> <span data-ttu-id="ade0a-554">Nell'esempio seguente viene definita una classe denominata `BaseClass` che non è conforme a CLS e una classe generica denominata `BaseCollection` il cui parametro di tipo deve derivare da `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-554">The following example defines a class named `BaseClass` that is not CLS-compliant and a generic class named `BaseCollection` whose type parameter must derive from `BaseClass`.</span></span> <span data-ttu-id="ade0a-555">Tuttavia, poiché `BaseClass` non è conforme a CLS, viene generato un avviso dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-555">But because `BaseClass` is not CLS-compliant, the compiler emits a warning.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

<span data-ttu-id="ade0a-556">Se un tipo generico è derivato da un tipo base generico, è necessario dichiarare nuovamente tutti i vincoli in modo che sia possibile garantire che vengano soddisfatti anche i vincoli sul tipo base.</span><span class="sxs-lookup"><span data-stu-id="ade0a-556">If a generic type is derived from a generic base type, it must redeclare any constraints so that it can guarantee that constraints on the base type are also satisfied.</span></span> <span data-ttu-id="ade0a-557">Nell'esempio riportato di seguito viene definito un oggetto `Number<T>` che può rappresentare qualsiasi tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="ade0a-557">The following example defines a `Number<T>` that can represent any numeric type.</span></span> <span data-ttu-id="ade0a-558">Viene anche definita una classe `FloatingPoint<T>` che rappresenta un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="ade0a-558">It also defines a `FloatingPoint<T>` class that represents a floating point value.</span></span> <span data-ttu-id="ade0a-559">Tuttavia, il codice sorgente non viene compilato, perché non viene applicato il vincolo su `Number<T>` (che T deve essere un tipo di valore) a `FloatingPoint<T>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-559">However, the source code fails to compile, because it does not apply the constraint on `Number<T>` (that T must be a value type) to `FloatingPoint<T>`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

<span data-ttu-id="ade0a-560">L'esempio viene compilato correttamente se il vincolo viene aggiunto alla classe `FloatingPoint<T>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-560">The example compiles successfully if the constraint is added to the `FloatingPoint<T>` class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

<span data-ttu-id="ade0a-561">Le specifiche CLS (Common Language Specification) impongono un modello conservativo per creazione di istanze per tipi annidati e membri protetti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-561">The Common Language Specification imposes a conservative per-instantiation model for nested types and protected members.</span></span> <span data-ttu-id="ade0a-562">Tramite i tipi generici aperti non è possibile esporre campi o membri con firme contenenti la creazione di un'istanza specifica di un tipo generico annidato e protetto.</span><span class="sxs-lookup"><span data-stu-id="ade0a-562">Open generic types cannot expose fields or members with signatures that contain a specific instantiation of a nested, protected generic type.</span></span> <span data-ttu-id="ade0a-563">Tramite i tipi non generici, mediante i quali viene estesa la creazione di un'istanza specifica di un'interfaccia o di una classe di base generica, non è possibile esporre i campi o i membri con firme contenenti la creazione di un'istanza differente di un tipo generico annidato e protetto.</span><span class="sxs-lookup"><span data-stu-id="ade0a-563">Non-generic types that extend a specific instantiation of a generic base class or interface cannot expose fields or members with signatures that contain a different instantiation of a nested, protected generic type.</span></span>

<span data-ttu-id="ade0a-564">Nell'esempio seguente vengono definiti un tipo generico, `C1<T>`, e una classe protetta `C1<T>.N`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-564">The following example defines a generic type, `C1<T>`, and a protected class, `C1<T>.N`.</span></span> <span data-ttu-id="ade0a-565">L'oggetto `C1<T>` dispone di due metodi: `M1` e `M2`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-565">`C1<T>` has two methods, `M1` and `M2`.</span></span> <span data-ttu-id="ade0a-566">Tuttavia, `M1` non è conforme a CLS poiché tenta di restituire un oggetto `C1<int>.N` da `C1<T>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-566">However, `M1` is not CLS-compliant because it tries to return a `C1<int>.N` object from `C1<T>`.</span></span> <span data-ttu-id="ade0a-567">Una seconda classe, `C2`, viene derivata da `C1<long>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-567">A second class, `C2`, is derived from `C1<long>`.</span></span> <span data-ttu-id="ade0a-568">Dispone di due metodi, `M3` e `M4`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-568">It has two methods, `M3` and `M4`.</span></span> <span data-ttu-id="ade0a-569">`M3` non è conforme a CLS perché prova a restituire un oggetto `C1<int>.N` da una sottoclasse di `C1<long>`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-569">`M3` is not CLS-compliant because it tries to return a `C1<int>.N` object from a subclass of `C1<long>`.</span></span> <span data-ttu-id="ade0a-570">I compilatori di linguaggio possono essere ancora più restrittivi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-570">Language compilers can be even more restrictive.</span></span> <span data-ttu-id="ade0a-571">In questo esempio in Visual Basic viene visualizzato un errore quando viene eseguito un tentativo di compilazione di `M4`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-571">In this example, Visual Basic displays an error when it tries to compile `M4`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a><span data-ttu-id="ade0a-572">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ade0a-572">Constructors</span></span>

<span data-ttu-id="ade0a-573">I costruttori nelle classi e strutture conformi a CLS devono rispettare queste regole:</span><span class="sxs-lookup"><span data-stu-id="ade0a-573">Constructors in CLS-compliant classes and structures must follow these rules:</span></span>

* <span data-ttu-id="ade0a-574">Prima di accedere ai dati di istanza ereditati, un costruttore di una classe derivata deve chiamare il costruttore di istanze della relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="ade0a-574">A constructor of a derived class must call the instance constructor of its base class before it accesses inherited instance data.</span></span> <span data-ttu-id="ade0a-575">Questo requisito è dovuto al fatto che i costruttori della classe di base non vengono ereditati dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="ade0a-575">This requirement is due to the fact that base class constructors are not inherited by their derived classes.</span></span> <span data-ttu-id="ade0a-576">Questa regola non si applica alle strutture, che non supportano l'ereditarietà diretta.</span><span class="sxs-lookup"><span data-stu-id="ade0a-576">This rule does not apply to structures, which do not support direct inheritance.</span></span>

  <span data-ttu-id="ade0a-577">In genere, questa regola viene applicata dai compilatori indipendentemente dalla conformità a CLS, come illustrato dall'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-577">Typically, compilers enforce this rule independently of CLS compliance, as the following example shows.</span></span> <span data-ttu-id="ade0a-578">Viene creata una classe `Doctor` derivata da una classe `Person`, ma la classe `Doctor` non riuscirà a chiamare il costruttore della classe `Person` per inizializzare i campi di istanza ereditati.</span><span class="sxs-lookup"><span data-stu-id="ade0a-578">It creates a `Doctor` class that is derived from a `Person` class, but the `Doctor` class fails to call the `Person` class constructor to initialize inherited instance fields.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* <span data-ttu-id="ade0a-579">Il costruttore di un oggetto non può essere chiamato tranne che per creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ade0a-579">An object constructor cannot be called except to create an object.</span></span> <span data-ttu-id="ade0a-580">Inoltre, un oggetto non può essere inizializzato due volte.</span><span class="sxs-lookup"><span data-stu-id="ade0a-580">In addition, an object cannot be initialized twice.</span></span> <span data-ttu-id="ade0a-581">Ad esempio, questo significa che `Object.MemberwiseClone` non deve chiamare i costruttori.</span><span class="sxs-lookup"><span data-stu-id="ade0a-581">For example, this means that `Object.MemberwiseClone` must not call constructors.</span></span>

### <a name="properties"></a><span data-ttu-id="ade0a-582">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade0a-582">Properties</span></span>

<span data-ttu-id="ade0a-583">Le proprietà nei tipi conformi a CLS devono rispettare queste regole:</span><span class="sxs-lookup"><span data-stu-id="ade0a-583">Properties in CLS-compliant types must follow these rules:</span></span>

* <span data-ttu-id="ade0a-584">Una proprietà deve disporre di un metodo Set, un metodo Get o di entrambi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-584">A property must have a setter, a getter, or both.</span></span> <span data-ttu-id="ade0a-585">In un assembly questi vengono implementati come metodi speciali, pertanto verranno visualizzati come metodi separati (il getter è denominato `get` \_ *PropertyName* e il setter è `set` \_ *PropertyName*) contrassegnato come `SpecialName` nei metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ade0a-585">In an assembly, these are implemented as special methods, which means that they will appear as separate methods (the getter is named `get`\_*propertyname* and the setter is `set`\_*propertyname*) marked as `SpecialName` in the assembly's metadata.</span></span> <span data-ttu-id="ade0a-586">Il compilatore C# applica questa regola automaticamente, senza la necessità di usare l'attributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ade0a-586">The C# compiler enforces this rule automatically without the need to apply the <xref:System.CLSCompliantAttribute> attribute.</span></span>

* <span data-ttu-id="ade0a-587">Un tipo di proprietà è il tipo restituito del metodo Get della proprietà e l'ultimo argomento del metodo Set.</span><span class="sxs-lookup"><span data-stu-id="ade0a-587">A property's type is the return type of the property getter and the last argument of the setter.</span></span> <span data-ttu-id="ade0a-588">È necessario che questi tipi siano conformi a CLS e gli argomenti non possono essere assegnati alla proprietà per riferimento, cioè non possono essere puntatori gestiti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-588">These types must be CLS compliant, and arguments cannot be assigned to the property by reference (that is, they cannot be managed pointers).</span></span>

* <span data-ttu-id="ade0a-589">Se una proprietà dispone dei metodi Get e Set, essi devono essere entrambi virtuali, statici o istanze.</span><span class="sxs-lookup"><span data-stu-id="ade0a-589">If a property has both a getter and a setter, they must both be virtual, both static, or both instance.</span></span> <span data-ttu-id="ade0a-590">Il compilatore C# applica automaticamente questa regola tramite la relativa sintassi di definizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="ade0a-590">The C# compiler automatically enforces this rule through property definition syntax.</span></span>

### <a name="events"></a><span data-ttu-id="ade0a-591">Eventi</span><span class="sxs-lookup"><span data-stu-id="ade0a-591">Events</span></span>

<span data-ttu-id="ade0a-592">Un evento viene definito in base al nome e al relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-592">An event is defined by its name and its type.</span></span> <span data-ttu-id="ade0a-593">Il tipo di evento è un delegato che viene usato per indicare l'evento.</span><span class="sxs-lookup"><span data-stu-id="ade0a-593">The event type is a delegate that is used to indicate the event.</span></span> <span data-ttu-id="ade0a-594">Ad esempio, l'evento `DbConnection.StateChange` è di tipo `StateChangeEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-594">For example, the `DbConnection.StateChange` event is of type `StateChangeEventHandler`.</span></span> <span data-ttu-id="ade0a-595">Oltre all'evento stesso, vi sono tre metodi con nomi basati sul nome di evento che forniscono l'implementazione dell'evento e sono contrassegnati come `SpecialName` nei metadati dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="ade0a-595">In addition to the event itself, three methods with names based on the event name provide the event's implementation and are marked as `SpecialName` in the assembly's metadata:</span></span>

* <span data-ttu-id="ade0a-596">Metodo per l'aggiunta di un gestore eventi, denominato `add` _*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ade0a-596">A method for adding an event handler, named `add`_*EventName*.</span></span> <span data-ttu-id="ade0a-597">Ad esempio, il metodo di sottoscrizione evento per l'evento `DbConnection.StateChange` è denominato `add_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-597">For example, the event subscription method for the `DbConnection.StateChange` event is named `add_StateChange`.</span></span>

* <span data-ttu-id="ade0a-598">Metodo per la rimozione di un gestore eventi, denominato `remove` _*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ade0a-598">A method for removing an event handler, named `remove`_*EventName*.</span></span> <span data-ttu-id="ade0a-599">Ad esempio, il metodo di rimozione per l'evento `DbConnection.StateChange` è denominato `remove_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-599">For example, the removal method for the `DbConnection.StateChange` event is named `remove_StateChange`.</span></span>

* <span data-ttu-id="ade0a-600">Un metodo per indicare che si è verificato l'evento, denominato `raise`\_*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ade0a-600">A method for indicating that the event has occurred, named `raise`\_*EventName*.</span></span>

> [!NOTE]
> <span data-ttu-id="ade0a-601">La maggior parte delle regole di Common Language Specification relative agli eventi viene implementata dai compilatori di linguaggi e risulta trasparente agli sviluppatori di componenti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-601">Most of the Common Language Specification's rules regarding events are implemented by language compilers and are transparent to component developers.</span></span>

<span data-ttu-id="ade0a-602">I metodi per l'aggiunta, la rimozione e la generazione di eventi devono avere la stessa accessibilità.</span><span class="sxs-lookup"><span data-stu-id="ade0a-602">The methods for adding, removing, and raising the event must have the same accessibility.</span></span> <span data-ttu-id="ade0a-603">Devono anche essere tutti statici, istanze o virtuali.</span><span class="sxs-lookup"><span data-stu-id="ade0a-603">They must also all be static, instance, or virtual.</span></span> <span data-ttu-id="ade0a-604">I metodi per l'aggiunta e la rimozione di un evento dispongono di un parametro il cui tipo è il tipo delegato di evento.</span><span class="sxs-lookup"><span data-stu-id="ade0a-604">The methods for adding and removing an event have one parameter whose type is the event delegate type.</span></span> <span data-ttu-id="ade0a-605">I metodi di aggiunta e rimozione devono essere entrambi presenti o entrambi assenti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-605">The add and remove methods must both be present or both be absent.</span></span>

<span data-ttu-id="ade0a-606">Nell'esempio seguente viene definita una classe conforme a CLS denominata `Temperature` tramite cui viene generato un evento `TemperatureChanged` se la modifica nella temperatura tra due letture è uguale o maggiore di un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="ade0a-606">The following example defines a CLS-compliant class named `Temperature` that raises a `TemperatureChanged` event if the change in temperature between two readings equals or exceeds a threshold value.</span></span> <span data-ttu-id="ade0a-607">Tramite la classe `Temperature` viene definito in modo esplicito un metodo `raise_TemperatureChanged` in modo che tramite esso sia possibile eseguire selettivamente i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-607">The `Temperature` class explicitly defines a `raise_TemperatureChanged` method so that it can selectively execute event handlers.</span></span>

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a><span data-ttu-id="ade0a-608">Overload</span><span class="sxs-lookup"><span data-stu-id="ade0a-608">Overloads</span></span>

<span data-ttu-id="ade0a-609">Le specifiche CLS (Common Language Specification) impongono i requisiti seguenti sui membri di overload:</span><span class="sxs-lookup"><span data-stu-id="ade0a-609">The Common Language Specification imposes the following requirements on overloaded members:</span></span>

* <span data-ttu-id="ade0a-610">I membri possono essere sottoposti a overload in base al numero di parametri e al tipo di qualsiasi parametro.</span><span class="sxs-lookup"><span data-stu-id="ade0a-610">Members can be overloaded based on the number of parameters and the type of any parameter.</span></span> <span data-ttu-id="ade0a-611">La convenzione di chiamata, il tipo restituito, i modificatori personalizzati applicati al metodo o al relativo parametro e se i parametri vengono passati per valore o per riferimento vengono ignorati quando viene fatta distinzione tra gli overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-611">Calling convention, return type, custom modifiers applied to the method or its parameter, and whether parameters are passed by value or by reference are not considered when differentiating between overloads.</span></span> <span data-ttu-id="ade0a-612">Per un esempio, vedere il codice relativo al requisito in cui viene richiesto che i nomi siano univoci all'interno di un ambito nella sezione [Convenzioni di denominazione](#naming-conventions).</span><span class="sxs-lookup"><span data-stu-id="ade0a-612">For an example, see the code for the requirement that names must be unique within a scope in the [Naming conventions](#naming-conventions) section.</span></span>

* <span data-ttu-id="ade0a-613">È possibile eseguire l'overload solo di proprietà e metodi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-613">Only properties and methods can be overloaded.</span></span> <span data-ttu-id="ade0a-614">Non è possibile eseguire l'overload di campi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-614">Fields and events cannot be overloaded.</span></span>

* <span data-ttu-id="ade0a-615">I metodi generici possono essere sottoposti a overload in base al numero dei relativi parametri generici.</span><span class="sxs-lookup"><span data-stu-id="ade0a-615">Generic methods can be overloaded based on the number of their generic parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="ade0a-616">Gli operatori `op_Explicit` e `op_Implicit` sono eccezioni alla regola che il valore restituito non viene considerato parte di una firma del metodo per risoluzione dell'overload.</span><span class="sxs-lookup"><span data-stu-id="ade0a-616">The `op_Explicit` and `op_Implicit` operators are exceptions to the rule that return value is not considered part of a method signature for overload resolution.</span></span> <span data-ttu-id="ade0a-617">Questi due operatori possono essere sottoposti a overload in base ai relativi parametri e al relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="ade0a-617">These two operators can be overloaded based on both their parameters and their return value.</span></span>

### <a name="exceptions"></a><span data-ttu-id="ade0a-618">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ade0a-618">Exceptions</span></span>

<span data-ttu-id="ade0a-619">Gli oggetti eccezione devono derivare da [System.Exception](xref:System.Exception) o da un altro tipo derivato da `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-619">Exception objects must derive from [System.Exception](xref:System.Exception) or from another type derived from `System.Exception`.</span></span> <span data-ttu-id="ade0a-620">Nell'esempio seguente viene illustrato l'errore del compilatore generato quando una classe personalizzata denominata `ErrorClass` viene usata per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ade0a-620">The following example illustrates the compiler error that results when a custom class named `ErrorClass` is used for exception handling.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

<span data-ttu-id="ade0a-621">Per correggere questo errore, la classe `ErrorClass` deve ereditare da `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-621">To correct this error, the `ErrorClass` class must inherit from `System.Exception`.</span></span> <span data-ttu-id="ade0a-622">Inoltre, la proprietà Message deve essere sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="ade0a-622">In addition, the Message property must be overridden.</span></span> <span data-ttu-id="ade0a-623">Nell'esempio riportato di seguito questi errori vengono corretti per definire una classe `ErrorClass` che è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-623">The following example corrects these errors to define an `ErrorClass` class that is CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a><span data-ttu-id="ade0a-624">Attributi</span><span class="sxs-lookup"><span data-stu-id="ade0a-624">Attributes</span></span>

<span data-ttu-id="ade0a-625">Negli assembly .NET Framework, gli attributi personalizzati forniscono un meccanismo estensibile per archiviare gli attributi personalizzati e recuperare i metadati sugli oggetti di programmazione, ad esempio assembly, tipi, membri e parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-625">In.NET Framework assemblies, custom attributes provide an extensible mechanism for storing custom attributes and retrieving metadata about programming objects, such as assemblies, types, members, and method parameters.</span></span> <span data-ttu-id="ade0a-626">Gli attributi personalizzati devono derivare da [System.Attribute](xref:System.Attribute) o da un tipo derivato da `System.Attribute`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-626">Custom attributes must derive from [System.Attribute](xref:System.Attribute) or from a type derived from `System.Attribute`.</span></span>

<span data-ttu-id="ade0a-627">Nell'esempio riportato di seguito viene violata questa regola.</span><span class="sxs-lookup"><span data-stu-id="ade0a-627">The following example violates this rule.</span></span> <span data-ttu-id="ade0a-628">Viene definita una classe `NumericAttribute` che non deriva da `System.Attribute`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-628">It defines a `NumericAttribute` class that does not derive from `System.Attribute`.</span></span> <span data-ttu-id="ade0a-629">Un errore del compilatore risulta solo quando viene applicato l'attributo non conforme a CLS, non quando la classe è definita.</span><span class="sxs-lookup"><span data-stu-id="ade0a-629">A compiler error results only when the non-CLS-compliant attribute is applied, not when the class is defined.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

<span data-ttu-id="ade0a-630">Tramite il costruttore o le proprietà di un attributo conforme a CLS possono essere esposti solo i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ade0a-630">The constructor or the properties of a CLS-compliant attribute can expose only the following types:</span></span>

* [<span data-ttu-id="ade0a-631">Boolean</span><span class="sxs-lookup"><span data-stu-id="ade0a-631">Boolean</span></span>](xref:System.Boolean)

* [<span data-ttu-id="ade0a-632">Byte</span><span class="sxs-lookup"><span data-stu-id="ade0a-632">Byte</span></span>](xref:System.Byte)

* [<span data-ttu-id="ade0a-633">Char</span><span class="sxs-lookup"><span data-stu-id="ade0a-633">Char</span></span>](xref:System.Char)

* [<span data-ttu-id="ade0a-634">Double</span><span class="sxs-lookup"><span data-stu-id="ade0a-634">Double</span></span>](xref:System.Double)

* [<span data-ttu-id="ade0a-635">Int16</span><span class="sxs-lookup"><span data-stu-id="ade0a-635">Int16</span></span>](xref:System.Int16)

* [<span data-ttu-id="ade0a-636">Int32</span><span class="sxs-lookup"><span data-stu-id="ade0a-636">Int32</span></span>](xref:System.Int32)

* [<span data-ttu-id="ade0a-637">Int64</span><span class="sxs-lookup"><span data-stu-id="ade0a-637">Int64</span></span>](xref:System.Int64)

* [<span data-ttu-id="ade0a-638">Single</span><span class="sxs-lookup"><span data-stu-id="ade0a-638">Single</span></span>](xref:System.Single)

* [<span data-ttu-id="ade0a-639">Stringa</span><span class="sxs-lookup"><span data-stu-id="ade0a-639">String</span></span>](xref:System.String)

* [<span data-ttu-id="ade0a-640">Tipo</span><span class="sxs-lookup"><span data-stu-id="ade0a-640">Type</span></span>](xref:System.Type)

* <span data-ttu-id="ade0a-641">Qualsiasi tipo di enumerazione il cui tipo sottostante è `Byte`, `Int16`, `Int32` o `Int64`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-641">Any enumeration type whose underlying type is `Byte`, `Int16`, `Int32`, or `Int64`.</span></span>

<span data-ttu-id="ade0a-642">Nell'esempio seguente viene definita una classe `DescriptionAttribute` che deriva da [Attribute](xref:System.Attribute).</span><span class="sxs-lookup"><span data-stu-id="ade0a-642">The following example defines a `DescriptionAttribute` class that derives from [Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="ade0a-643">Il costruttore di classe dispone di un parametro di tipo `Descriptor`, pertanto la classe non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-643">The class constructor has a parameter of type `Descriptor`, so the class is not CLS-compliant.</span></span> <span data-ttu-id="ade0a-644">Il compilatore C# genera un avviso, ma viene compilato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ade0a-644">The C# compiler emits a warning but compiles successfully.</span></span>

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a><span data-ttu-id="ade0a-645">Attributo CLSCompliantAttribute</span><span class="sxs-lookup"><span data-stu-id="ade0a-645">The CLSCompliantAttribute attribute</span></span>

<span data-ttu-id="ade0a-646">L'attributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) è usato per indicare se un elemento del programma è conforme a CLS (Common Language Specification).</span><span class="sxs-lookup"><span data-stu-id="ade0a-646">The [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is used to indicate whether a program element complies with the Common Language Specification.</span></span> <span data-ttu-id="ade0a-647">Il costruttore `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` include un solo parametro obbligatorio, *isCompliant*, che indica se l'elemento del programma è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-647">The `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` constructor includes a single required parameter, *isCompliant*, that indicates whether the program element is CLS-compliant.</span></span>

<span data-ttu-id="ade0a-648">In fase di compilazione, tramite il compilatore vengono rilevati gli elementi non conformi che si presuppone siano conformi a CLS e viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-648">At compile time, the compiler detects non-compliant elements that are presumed to be CLS-compliant and emits a warning.</span></span> <span data-ttu-id="ade0a-649">Tramite il compilatore non vengono generati avvisi per i tipi o i membri che vengono dichiarati esplicitamente come non conformi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-649">The compiler does not emit warnings for types or members that are explicitly declared to be non-compliant.</span></span>

<span data-ttu-id="ade0a-650">Gli sviluppatori di componenti possono usare l'attributo `CLSCompliantAttribute` in due modi:</span><span class="sxs-lookup"><span data-stu-id="ade0a-650">Component developers can use the `CLSCompliantAttribute` attribute in two ways:</span></span>

* <span data-ttu-id="ade0a-651">Per definire le parti dell'interfaccia pubblica esposte da un componente che sono conformi a CLS e le parti che non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-651">To define the parts of the public interface exposed by a component that are CLS-compliant and the parts that are not CLS-compliant.</span></span> <span data-ttu-id="ade0a-652">Quando l'attributo viene usato per contrassegnare determinati elementi del programma come conformi a CLS, il relativo uso garantisce che gli elementi sono accessibili da tutti i linguaggi e strumenti destinati a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ade0a-652">When the attribute is used to mark particular program elements as CLS-compliant, its use guarantees that those elements are accessible from all languages and tools that target the .NET Framework.</span></span>

* <span data-ttu-id="ade0a-653">Per assicurarsi che tramite l'interfaccia pubblica della libreria componenti vengano esposti solo elementi del programma che sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-653">To ensure that the component library's public interface exposes only program elements that are CLS-compliant.</span></span> <span data-ttu-id="ade0a-654">Se gli elementi non sono conformi a CLS, tramite i compilatori viene di solito generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-654">If elements are not CLS-compliant, compilers will generally issue a warning.</span></span>

> [!WARNING]
> <span data-ttu-id="ade0a-655">In alcuni casi, dai compilatori di linguaggio vengono applicate regole conformi a CLS indipendentemente dal fatto che l'attributo `CLSCompliantAttribute` venga usato.</span><span class="sxs-lookup"><span data-stu-id="ade0a-655">In some cases, language compilers enforce CLS-compliant rules regardless of whether the `CLSCompliantAttribute` attribute is used.</span></span> <span data-ttu-id="ade0a-656">Ad esempio, con la definizione di un membro `*static` in un'interfaccia viene violata una regola CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-656">For example, defining a `*static` member in an interface violates a CLS rule.</span></span> <span data-ttu-id="ade0a-657">Tuttavia, se si definisce un membro `*static` in un'interfaccia, il compilatore C# visualizza un messaggio di errore e l'app non viene compilata.</span><span class="sxs-lookup"><span data-stu-id="ade0a-657">However, if you define a `*static` member in an interface, the C# compiler displays an error message and fails to compile the app.</span></span>

<span data-ttu-id="ade0a-658">L'attributo `CLSCompliantAttribute` è contrassegnato con un attributo [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) con un valore pari a `AttributeTargets.All`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-658">The `CLSCompliantAttribute` attribute is marked with an [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) attribute that has a value of `AttributeTargets.All`.</span></span> <span data-ttu-id="ade0a-659">Con questo valore è possibile applicare l'attributo `CLSCompliantAttribute` a qualsiasi elemento del programma, tra cui assembly, moduli, tipi (classi, strutture, enumerazioni, interfacce e delegati), membri di tipo (costruttori, metodi, proprietà, campi ed eventi), parametri, parametri generici e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-659">This value allows you to apply the `CLSCompliantAttribute` attribute to any program element, including assemblies, modules, types (classes, structures, enumerations, interfaces, and delegates), type members (constructors, methods, properties, fields, and events), parameters, generic parameters, and return values.</span></span> <span data-ttu-id="ade0a-660">Tuttavia, in pratica, è consigliabile applicare l'attributo solo agli assembly, ai tipi e ai membri di tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0a-660">However, in practice, you should apply the attribute only to assemblies, types, and type members.</span></span> <span data-ttu-id="ade0a-661">In caso contrario, tramite i compilatori viene ignorato l'attributo e viene continuata la generazione di avvisi del compilatore ogni volta che viene rilevato un parametro non conforme, un parametro generico o un valore restituito nell'interfaccia pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="ade0a-661">Otherwise, compilers ignore the attribute and continue to generate compiler warnings whenever they encounter a non-compliant parameter, generic parameter, or return value in your library's public interface.</span></span>

<span data-ttu-id="ade0a-662">Il valore dell'attributo `CLSCompliantAttribute` viene ereditato dagli elementi del programma contenuti.</span><span class="sxs-lookup"><span data-stu-id="ade0a-662">The value of the `CLSCompliantAttribute` attribute is inherited by contained program elements.</span></span> <span data-ttu-id="ade0a-663">Ad esempio, se un assembly è contrassegnato come conforme a CLS, anche i relativi tipi sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-663">For example, if an assembly is marked as CLS-compliant, its types are also CLS-compliant.</span></span> <span data-ttu-id="ade0a-664">Se un tipo è contrassegnato come conforme a CLS, anche i relativi membri e tipi annidati sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-664">If a type is marked as CLS-compliant, its nested types and members are also CLS-compliant.</span></span>

<span data-ttu-id="ade0a-665">È possibile eseguire l'override in modo esplicito della conformità ereditata applicando l'attributo `CLSCompliantAttribute` a un elemento del programma contenuto.</span><span class="sxs-lookup"><span data-stu-id="ade0a-665">You can explicitly override the inherited compliance by applying the `CLSCompliantAttribute` attribute to a contained program element.</span></span> <span data-ttu-id="ade0a-666">Ad esempio, è possibile usare l'attributo `CLSCompliantAttribute` con un valore *isCompliant*`false` per definire un tipo non conforme in un assembly conforme e l'attributo con un valore *isCompliant*`true` per definire un tipo conforme in un assembly non conforme.</span><span class="sxs-lookup"><span data-stu-id="ade0a-666">For example, you can use the `CLSCompliantAttribute` attribute with an *isCompliant* value of `false` to define a non-compliant type in a compliant assembly, and you can use the attribute with an *isCompliant* value of `true` to define a compliant type in a non-compliant assembly.</span></span> <span data-ttu-id="ade0a-667">È anche possibile definire i membri non conformi in un tipo conforme.</span><span class="sxs-lookup"><span data-stu-id="ade0a-667">You can also define non-compliant members in a compliant type.</span></span> <span data-ttu-id="ade0a-668">Tuttavia, in un tipo non conforme non possono essere inclusi membri conformi. Di conseguenza, non è possibile usare l'attributo con un valore *isCompliant*`true` per eseguire l'override dell'ereditarietà da un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="ade0a-668">However, a non-compliant type cannot have compliant members, so you cannot use the attribute with an *isCompliant* value of `true` to override inheritance from a non-compliant type.</span></span>

<span data-ttu-id="ade0a-669">Quando si sviluppano componenti, è sempre consigliabile usare l'attributo `CLSCompliantAttribute` per indicare se l'assembly e i relativi tipi e membri sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-669">When you are developing components, you should always use the `CLSCompliantAttribute` attribute to indicate whether your assembly, its types, and its members are CLS-compliant.</span></span>

<span data-ttu-id="ade0a-670">Per creare componenti conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="ade0a-670">To create CLS-compliant components:</span></span>

1. <span data-ttu-id="ade0a-671">Usare l'oggetto `CLSCompliantAttribute` per contrassegnare l'assembly come conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-671">Use the `CLSCompliantAttribute` to mark you assembly as CLS-compliant.</span></span>

2. <span data-ttu-id="ade0a-672">Contrassegnare tutti i tipi esposti pubblicamente nell'assembly che non sono conformi a CLS come non conformi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-672">Mark any publicly exposed types in the assembly that are not CLS-compliant as non-compliant.</span></span>

3. <span data-ttu-id="ade0a-673">Contrassegnare tutti i membri esposti pubblicamente in tipi conformi a CLS come non conformi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-673">Mark any publicly exposed members in CLS-compliant types as non-compliant.</span></span>

4. <span data-ttu-id="ade0a-674">Fornire un'alternativa conforme a CLS per i membri non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-674">Provide a CLS-compliant alternative for non-CLS-compliant members.</span></span>

<span data-ttu-id="ade0a-675">Se sono stati contrassegnati correttamente tutti i tipi e i membri non conformi, tramite il compilatore non vengono generati avvisi di mancata conformità.</span><span class="sxs-lookup"><span data-stu-id="ade0a-675">If you've successfully marked all your non-compliant types and members, your compiler should not emit any non-compliance warnings.</span></span> <span data-ttu-id="ade0a-676">Tuttavia, è consigliabile indicare i membri che non sono conformi a CLS ed elencare le alternative conformi a CLS nella documentazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="ade0a-676">However, you should indicate which members are not CLS-compliant and list their CLS-compliant alternatives in your product documentation.</span></span>

<span data-ttu-id="ade0a-677">Nell'esempio seguente viene usato l'attributo `CLSCompliantAttribute` per definire un assembly conforme a CLS e un tipo, `CharacterUtilities`, contenente due membri non conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-677">The following example uses the `CLSCompliantAttribute` attribute to define a CLS-compliant assembly and a type, `CharacterUtilities`, that has two non-CLS-compliant members.</span></span> <span data-ttu-id="ade0a-678">Poiché entrambi i membri sono contrassegnati con l'attributo `CLSCompliant(false)`, non vengono generati avvisi dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="ade0a-678">Because both members are tagged with the `CLSCompliant(false)` attribute, the compiler produces no warnings.</span></span> <span data-ttu-id="ade0a-679">La classe fornisce anche un'alternativa conforme a CLS per entrambi i metodi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-679">The class also provides a CLS-compliant alternative for both methods.</span></span> <span data-ttu-id="ade0a-680">In genere, si aggiungono solo due overload al metodo `ToUTF16` per fornire alternative conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-680">Ordinarily, we would just add two overloads to the `ToUTF16` method to provide CLS-compliant alternatives.</span></span> <span data-ttu-id="ade0a-681">Tuttavia, poiché i metodi non possono essere sottoposti a overload in base al valore restituito, i nomi dei metodi conformi a CLS sono diversi da quelli dei metodi non conformi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-681">However, because methods cannot be overloaded based on return value, the names of the CLS-compliant methods are different from the names of the non-compliant methods.</span></span>

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

<span data-ttu-id="ade0a-682">Se si sta sviluppando un'applicazione anziché una libreria (cioè se non si stanno esponendo tipi o membri che possono essere usati da altri sviluppatori dell'applicazione), la conformità a CLS degli elementi del programma usati dall'applicazione è importante solo se il linguaggio non li supporta.</span><span class="sxs-lookup"><span data-stu-id="ade0a-682">If you are developing an app rather than a library (that is, if you aren't exposing types or members that can be consumed by other app developers), the CLS compliance of the program elements that your app consumes are of interest only if your language does not support them.</span></span> <span data-ttu-id="ade0a-683">In questo caso, tramite il compilatore di linguaggio verrà generato un errore quando si tenta di usare un elemento non conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ade0a-683">In that case, your language compiler will generate an error when you try to use a non-CLS-compliant element.</span></span>

## <a name="cross-language-interoperability"></a><span data-ttu-id="ade0a-684">Interoperabilità tra linguaggi diversi</span><span class="sxs-lookup"><span data-stu-id="ade0a-684">Cross-language interoperability</span></span>

<span data-ttu-id="ade0a-685">L'indipendenza del linguaggio ha numerosi significati possibili.</span><span class="sxs-lookup"><span data-stu-id="ade0a-685">Language independence has a number of possible meanings.</span></span> <span data-ttu-id="ade0a-686">Un significato riguarda l'utilizzo semplice dei tipi scritti in un linguaggio da parte di un'applicazione scritta in un linguaggio diverso.</span><span class="sxs-lookup"><span data-stu-id="ade0a-686">One meaning involves seamlessly consuming types written in one language from an app written in another language.</span></span> <span data-ttu-id="ade0a-687">Un secondo significato, che è il fulcro di questo articolo, riguarda la combinazione di codice scritto in più linguaggi in un unico assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ade0a-687">A second meaning, which is the focus of this article, involves combining code written in multiple languages into a single .NET Framework assembly.</span></span>

<span data-ttu-id="ade0a-688">L'esempio seguente illustra l'interoperabilità tra linguaggi mediante la creazione di una libreria di classi denominata Utilities.dll che comprende due classi, `NumericLib` e `StringLib`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-688">The following example illustrates cross-language interoperability by creating a class library named Utilities.dll that includes two classes, `NumericLib` and `StringLib`.</span></span> <span data-ttu-id="ade0a-689">La classe `NumericLib` è scritta in C# e la classe `StringLib` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ade0a-689">The `NumericLib` class is written in C#, and the `StringLib` class is written in Visual Basic.</span></span> <span data-ttu-id="ade0a-690">Di seguito è riportato il codice sorgente per `StringUtil.vb`, in cui è incluso un singolo membro, `ToTitleCase`, nella classe `StringLib`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-690">Here's the source code for `StringUtil.vb`, which includes a single member, `ToTitleCase`, in its `StringLib` class.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

<span data-ttu-id="ade0a-691">Di seguito è riportato il codice sorgente per NumberUtil.cs tramite cui viene definita una classe `NumericLib` in cui sono contenuti due membri, `IsEven` e `NearZero`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-691">Here's the source code for NumberUtil.cs, which defines a `NumericLib` class that has two members, `IsEven` and `NearZero`.</span></span>

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

<span data-ttu-id="ade0a-692">Per includere le due classi in un singolo assembly, è necessario compilarle in moduli.</span><span class="sxs-lookup"><span data-stu-id="ade0a-692">To package the two classes in a single assembly, you must compile them into modules.</span></span> <span data-ttu-id="ade0a-693">Per compilare il file di codice sorgente di Visual Basic in un modulo, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ade0a-693">To compile the Visual Basic source code file into a module, use this command:</span></span>

```console
vbc /t:module StringUtil.vb
```

<span data-ttu-id="ade0a-694">Per compilare il file di codice sorgente di C# in un modulo, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ade0a-694">To compile the C# source code file into a module, use this command:</span></span>

```console
csc /t:module NumberUtil.cs
```

<span data-ttu-id="ade0a-695">Usare quindi lo strumento Link (Link.exe) per compilare i due moduli in un assembly:</span><span class="sxs-lookup"><span data-stu-id="ade0a-695">You then use the Link tool (Link.exe) to compile the two modules into an assembly:</span></span>

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

<span data-ttu-id="ade0a-696">L'esempio seguente chiama quindi i metodi `NumericLib.NearZero` e `StringLib.ToTitleCase`.</span><span class="sxs-lookup"><span data-stu-id="ade0a-696">The following example then calls the `NumericLib.NearZero` and `StringLib.ToTitleCase` methods.</span></span> <span data-ttu-id="ade0a-697">Sia il codice Visual Basic che il codice C# sono in grado di accedere ai metodi in entrambe le classi.</span><span class="sxs-lookup"><span data-stu-id="ade0a-697">Both the Visual Basic code and the C# code are able to access the methods in both classes.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

<span data-ttu-id="ade0a-698">Per compilare il codice Visual Basic, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ade0a-698">To compile the Visual Basic code, use this command:</span></span>

```console
vbc example.vb /r:UtilityLib.dll
```

<span data-ttu-id="ade0a-699">Per eseguire la compilazione con C#, modificare il nome del compilatore da vbc a csc e modificare l'estensione del file da vb a cs:</span><span class="sxs-lookup"><span data-stu-id="ade0a-699">To compile with C#, change the name of the compiler from vbc to csc, and change the file extension from .vb to .cs:</span></span>

```console
csc example.cs /r:UtilityLib.dll
```
