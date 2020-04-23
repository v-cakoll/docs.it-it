---
title: Specifica di nomi di tipo completi
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: 707c71482196d789ed9a88db34af048ec57734fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130023"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="28578-102">Specifica di nomi di tipo completi</span><span class="sxs-lookup"><span data-stu-id="28578-102">Specifying fully qualified type names</span></span>

<span data-ttu-id="28578-103">È necessario specificare nomi di tipi per avere input validi per le diverse operazioni di reflection.</span><span class="sxs-lookup"><span data-stu-id="28578-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="28578-104">Un nome completo consiste in una specifica del nome di assembly, in una specifica dello spazio dei nomi e in un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="28578-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="28578-105">Le specifiche dei nomi di tipi vengono usate dai metodi, quali <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> e <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28578-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="28578-106">Grammatica per i nomi dei tipi</span><span class="sxs-lookup"><span data-stu-id="28578-106">Grammar for type names</span></span>

 <span data-ttu-id="28578-107">La grammatica definisce la sintassi di linguaggi formali.</span><span class="sxs-lookup"><span data-stu-id="28578-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="28578-108">La tabella seguente elenca le regole lessicali che descrivono come riconoscere un input valido.</span><span class="sxs-lookup"><span data-stu-id="28578-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="28578-109">I terminali (ovvero gli elementi che non sono ulteriormente riducibili) vengono visualizzati in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="28578-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="28578-110">I non terminali (ovvero gli elementi che sono ulteriormente riducibili) vengono visualizzati in stringhe miste di maiuscole e minuscole o in stringhe tra virgolette singole, ma la virgoletta singola (') non è parte della sintassi stessa.</span><span class="sxs-lookup"><span data-stu-id="28578-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="28578-111">Il carattere barra verticale (& #124;) indica regole che includono sottoregole.</span><span class="sxs-lookup"><span data-stu-id="28578-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="28578-112">Specifica di caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="28578-112">Specifying special characters</span></span>

<span data-ttu-id="28578-113">In un nome di tipo, IDENTIFIER corrisponde a un qualsiasi nome valido determinato dalle regole di un linguaggio.</span><span class="sxs-lookup"><span data-stu-id="28578-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="28578-114">Usare la barra rovesciata (\\) come carattere di escape per separare i token seguenti quando vengono usati come parte di IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="28578-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="28578-115">token</span><span class="sxs-lookup"><span data-stu-id="28578-115">Token</span></span>|<span data-ttu-id="28578-116">Significato</span><span class="sxs-lookup"><span data-stu-id="28578-116">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="28578-117">\\,</span><span class="sxs-lookup"><span data-stu-id="28578-117">\\,</span></span>|<span data-ttu-id="28578-118">Separatore di assembly.</span><span class="sxs-lookup"><span data-stu-id="28578-118">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="28578-119">Separatore di tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="28578-119">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="28578-120">Tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="28578-120">Reference type.</span></span>|
|\\*|<span data-ttu-id="28578-121">Tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="28578-121">Pointer type.</span></span>|
|<span data-ttu-id="28578-122">\\[</span><span class="sxs-lookup"><span data-stu-id="28578-122">\\[</span></span>|<span data-ttu-id="28578-123">Delimitatore delle dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="28578-123">Array dimension delimiter.</span></span>|
|<span data-ttu-id="28578-124">\\]</span><span class="sxs-lookup"><span data-stu-id="28578-124">\\]</span></span>|<span data-ttu-id="28578-125">Delimitatore delle dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="28578-125">Array dimension delimiter.</span></span>|
|<span data-ttu-id="28578-126">\\.</span><span class="sxs-lookup"><span data-stu-id="28578-126">\\.</span></span>|<span data-ttu-id="28578-127">Usare la barra rovesciata prima di un punto solo se il punto è usato in una specifica di matrice.</span><span class="sxs-lookup"><span data-stu-id="28578-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="28578-128">I punti in NamespaceSpec non accettano la barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="28578-128">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="28578-129">\\\|Barra rovesciata se necessaria come stringa letterale.</span><span class="sxs-lookup"><span data-stu-id="28578-129">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="28578-130">Si noti che in tutti i componenti TypeSpec, ad eccezione di AssemblyNameSpec, gli spazi sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="28578-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="28578-131">In AssemblyNameSpec, gli spazi che precedono il separatore ',' sono rilevanti, ma gli spazi dopo il separatore ',' vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="28578-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="28578-132">Le classi reflection, ad esempio <xref:System.Type.FullName%2A?displayProperty=nameWithType>, restituiscono il nome modificato in modo che possa essere usato in una chiamata a <xref:System.Type.GetType%2A>, ad esempio in `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="28578-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="28578-133">Ad esempio, il nome completo per un tipo potrebbe essere `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="28578-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="28578-134">Se lo spazio dei nomi fosse `Ozzy.Out+Back`, il segno di addizione dovrebbe essere preceduto da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="28578-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="28578-135">In caso contrario, il parser lo interpreterebbe come separatore di annidamento.</span><span class="sxs-lookup"><span data-stu-id="28578-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="28578-136">Reflection genera questa stringa come `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="28578-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="28578-137">Specifica dei nomi di assembly</span><span class="sxs-lookup"><span data-stu-id="28578-137">Specifying assembly names</span></span>

<span data-ttu-id="28578-138">Le informazioni minime necessarie in una specifica di nome di assembly è il nome testuale (IDENTIFIER) dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="28578-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="28578-139">È possibile far seguire l'IDENTIFIER da un elenco delimitato da virgole di coppie proprietà/valore, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="28578-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="28578-140">La denominazione dell'IDENTIFIER deve seguire le regole di denominazione dei file.</span><span class="sxs-lookup"><span data-stu-id="28578-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="28578-141">La denominazione dell'IDENTIFIER non fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="28578-141">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="28578-142">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="28578-142">Property name</span></span>|<span data-ttu-id="28578-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28578-143">Description</span></span>|<span data-ttu-id="28578-144">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="28578-144">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="28578-145">**Versione**</span><span class="sxs-lookup"><span data-stu-id="28578-145">**Version**</span></span>|<span data-ttu-id="28578-146">Numero di versione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="28578-146">Assembly version number</span></span>|<span data-ttu-id="28578-147">*Major.Minor.Build.Revision*, dove *Major*, *Minor*, *Build* e *Revision* sono numeri interi compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="28578-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="28578-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="28578-148">**PublicKey**</span></span>|<span data-ttu-id="28578-149">Chiave pubblica completa</span><span class="sxs-lookup"><span data-stu-id="28578-149">Full public key</span></span>|<span data-ttu-id="28578-150">Valore di stringa della chiave pubblica completa in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="28578-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="28578-151">Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.</span><span class="sxs-lookup"><span data-stu-id="28578-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="28578-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="28578-152">**PublicKeyToken**</span></span>|<span data-ttu-id="28578-153">Token di chiave pubblica (hash a 8 byte della chiave pubblica completa)</span><span class="sxs-lookup"><span data-stu-id="28578-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="28578-154">Valore di stringa del token della chiave pubblica in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="28578-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="28578-155">Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.</span><span class="sxs-lookup"><span data-stu-id="28578-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="28578-156">**Impostazioni cultura**</span><span class="sxs-lookup"><span data-stu-id="28578-156">**Culture**</span></span>|<span data-ttu-id="28578-157">Impostazioni cultura dell'assembly</span><span class="sxs-lookup"><span data-stu-id="28578-157">Assembly culture</span></span>|<span data-ttu-id="28578-158">Impostazioni cultura dell'assembly in formato RFC 1766 o "neutral" per gli assembly indipendenti dal linguaggio (non satellite).</span><span class="sxs-lookup"><span data-stu-id="28578-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="28578-159">**Impostazione personalizzata**</span><span class="sxs-lookup"><span data-stu-id="28578-159">**Custom**</span></span>|<span data-ttu-id="28578-160">BLOB (Binary Large Object, Oggetto binario di grandi dimensioni) personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28578-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="28578-161">Attualmente viene usato solo in assembly generati dal [generatore di immagini native (Ngen)](../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="28578-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="28578-162">Stringa personalizzata usata dal generatore di immagini native per notificare alla cache di assembly che l'assembly che si sta installando è un'immagine nativa e deve pertanto essere installato nella cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="28578-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="28578-163">Nota anche come stringa zap.</span><span class="sxs-lookup"><span data-stu-id="28578-163">Also called a zap string.</span></span>|

<span data-ttu-id="28578-164">L'esempio seguente illustra un **AssemblyName** per un assembly a nome semplice con le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="28578-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="28578-165">L'esempio seguente illustra un riferimento completo per un assembly con nome sicuro nelle impostazioni cultura "en" (inglese).</span><span class="sxs-lookup"><span data-stu-id="28578-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="28578-166">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che può essere soddisfatto da un assembly con nome sicuro o semplice.</span><span class="sxs-lookup"><span data-stu-id="28578-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="28578-167">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome semplice.</span><span class="sxs-lookup"><span data-stu-id="28578-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="28578-168">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="28578-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="28578-169">Specifica di tipi generici</span><span class="sxs-lookup"><span data-stu-id="28578-169">Specifying generic types</span></span>

<span data-ttu-id="28578-170">SimpleTypeSpec\`NUMERO rappresenta un tipo generico aperto con parametri di tipo generico compresi tra 1 e *n*.</span><span class="sxs-lookup"><span data-stu-id="28578-170">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="28578-171">Ad esempio, per ottenere un riferimento al tipo generico aperto List\<T> o al tipo generico chiuso\<String>, usare ``Type.GetType("System.Collections.Generic.List`1")``. Per ottenere un riferimento al tipo generico Dictionary\<TKey,TValue>, usare ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span><span class="sxs-lookup"><span data-stu-id="28578-171">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="28578-172">Specifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="28578-172">Specifying pointers</span></span>

<span data-ttu-id="28578-173">SimpleTypeSpec\* rappresenta un puntatore non gestito.</span><span class="sxs-lookup"><span data-stu-id="28578-173">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="28578-174">Ad esempio, per ottenere un puntatore per il tipo MyType, usare `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="28578-174">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="28578-175">Per ottenere un puntatore a un puntatore per il tipo MyType, usare `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="28578-175">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="28578-176">Specifica dei riferimenti</span><span class="sxs-lookup"><span data-stu-id="28578-176">Specifying references</span></span>

<span data-ttu-id="28578-177">SimpleTypeSpec & rappresenta un riferimento o puntatore gestito.</span><span class="sxs-lookup"><span data-stu-id="28578-177">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="28578-178">Ad esempio, per ottenere un riferimento per il tipo MyType, usare `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="28578-178">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="28578-179">Si noti che, a differenza dei puntatori, i riferimenti sono limitati a un solo livello.</span><span class="sxs-lookup"><span data-stu-id="28578-179">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="28578-180">Specifica delle matrici</span><span class="sxs-lookup"><span data-stu-id="28578-180">Specifying arrays</span></span>

<span data-ttu-id="28578-181">Nella grammatica BNF, ReflectionEmitDimension si applica solo a definizioni di tipi incomplete recuperate tramite <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28578-181">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28578-182">Le definizioni di tipi incomplete sono oggetti <xref:System.Reflection.Emit.TypeBuilder> costruiti tramite <xref:System.Reflection.Emit?displayProperty=nameWithType> senza chiamare <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28578-182">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="28578-183">ReflectionDimension può essere usato per recuperare qualsiasi definizione di tipo che è stata completata, vale a dire, un tipo che è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="28578-183">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="28578-184">Le matrici sono accessibili in reflection specificando l'ordine della matrice:</span><span class="sxs-lookup"><span data-stu-id="28578-184">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="28578-185">`Type.GetType("MyArray[]")` ottiene una matrice unidimensionale con un limite inferiore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="28578-185">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="28578-186">`Type.GetType("MyArray[*]")` ottiene una matrice unidimensionale con un limite inferiore sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="28578-186">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="28578-187">`Type.GetType("MyArray[][]")` ottiene una matrice di matrice bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="28578-187">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="28578-188">`Type.GetType("MyArray[*,*]")` e `Type.GetType("MyArray[,]")` ottengono una matrice rettangolare bidimensionale con limiti inferiori sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="28578-188">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="28578-189">Si noti che dal punto di vista del runtime, `MyArray[] != MyArray[*]`, ma per le matrici multidimensionali, le due notazioni sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="28578-189">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="28578-190">Vale a dire, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` restituisce **true**.</span><span class="sxs-lookup"><span data-stu-id="28578-190">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="28578-191">Per **ModuleBuilder. GetType**, `MyArray[0..5]` indica una matrice a dimensione singola con dimensione 6, limite inferiore 0.</span><span class="sxs-lookup"><span data-stu-id="28578-191">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="28578-192">`MyArray[4…]` indica una matrice unidimensionale di dimensioni sconosciute e limite inferiore pari a 4.</span><span class="sxs-lookup"><span data-stu-id="28578-192">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="28578-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28578-193">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="28578-194">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="28578-194">Viewing Type Information</span></span>](viewing-type-information.md)
