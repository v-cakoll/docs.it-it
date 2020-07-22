---
title: Specifica di nomi di tipo completi
description: Per un input valido per le operazioni di reflection, usare nomi di tipo completi, che includono specifiche del nome di assembly, specifiche dello spazio dei nomi e nomi di tipi.
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
ms.openlocfilehash: ff33b6abd31a82c6b80aa794564c5c48648cde63
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865229"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="c0c68-103">Specifica di nomi di tipo completi</span><span class="sxs-lookup"><span data-stu-id="c0c68-103">Specifying fully qualified type names</span></span>

<span data-ttu-id="c0c68-104">È necessario specificare nomi di tipi per avere input validi per le diverse operazioni di reflection.</span><span class="sxs-lookup"><span data-stu-id="c0c68-104">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="c0c68-105">Un nome completo consiste in una specifica del nome di assembly, in una specifica dello spazio dei nomi e in un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="c0c68-105">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="c0c68-106">Le specifiche dei nomi di tipi vengono usate dai metodi, quali <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> e <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0c68-106">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="c0c68-107">Grammatica per i nomi dei tipi</span><span class="sxs-lookup"><span data-stu-id="c0c68-107">Grammar for type names</span></span>

 <span data-ttu-id="c0c68-108">La grammatica definisce la sintassi di linguaggi formali.</span><span class="sxs-lookup"><span data-stu-id="c0c68-108">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="c0c68-109">La tabella seguente elenca le regole lessicali che descrivono come riconoscere un input valido.</span><span class="sxs-lookup"><span data-stu-id="c0c68-109">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="c0c68-110">I terminali (ovvero gli elementi che non sono ulteriormente riducibili) vengono visualizzati in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="c0c68-110">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="c0c68-111">I non terminali (ovvero gli elementi che sono ulteriormente riducibili) vengono visualizzati in stringhe miste di maiuscole e minuscole o in stringhe tra virgolette singole, ma la virgoletta singola (') non è parte della sintassi stessa.</span><span class="sxs-lookup"><span data-stu-id="c0c68-111">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="c0c68-112">Il carattere barra verticale (& #124;) indica regole che includono sottoregole.</span><span class="sxs-lookup"><span data-stu-id="c0c68-112">The pipe character (&#124;) denotes rules that have subrules.</span></span>

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

## <a name="specifying-special-characters"></a><span data-ttu-id="c0c68-113">Specifica di caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="c0c68-113">Specifying special characters</span></span>

<span data-ttu-id="c0c68-114">In un nome di tipo, IDENTIFIER corrisponde a un qualsiasi nome valido determinato dalle regole di un linguaggio.</span><span class="sxs-lookup"><span data-stu-id="c0c68-114">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="c0c68-115">Usare la barra rovesciata (\\) come carattere di escape per separare i token seguenti quando vengono usati come parte di IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="c0c68-115">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="c0c68-116">token</span><span class="sxs-lookup"><span data-stu-id="c0c68-116">Token</span></span>|<span data-ttu-id="c0c68-117">Significato</span><span class="sxs-lookup"><span data-stu-id="c0c68-117">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="c0c68-118">\\,</span><span class="sxs-lookup"><span data-stu-id="c0c68-118">\\,</span></span>|<span data-ttu-id="c0c68-119">Separatore di assembly.</span><span class="sxs-lookup"><span data-stu-id="c0c68-119">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="c0c68-120">Separatore di tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="c0c68-120">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="c0c68-121">Tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c0c68-121">Reference type.</span></span>|
|\\*|<span data-ttu-id="c0c68-122">Tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="c0c68-122">Pointer type.</span></span>|
|<span data-ttu-id="c0c68-123">\\[</span><span class="sxs-lookup"><span data-stu-id="c0c68-123">\\[</span></span>|<span data-ttu-id="c0c68-124">Delimitatore delle dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="c0c68-124">Array dimension delimiter.</span></span>|
|<span data-ttu-id="c0c68-125">\\]</span><span class="sxs-lookup"><span data-stu-id="c0c68-125">\\]</span></span>|<span data-ttu-id="c0c68-126">Delimitatore delle dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="c0c68-126">Array dimension delimiter.</span></span>|
|<span data-ttu-id="c0c68-127">\\.</span><span class="sxs-lookup"><span data-stu-id="c0c68-127">\\.</span></span>|<span data-ttu-id="c0c68-128">Usare la barra rovesciata prima di un punto solo se il punto è usato in una specifica di matrice.</span><span class="sxs-lookup"><span data-stu-id="c0c68-128">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="c0c68-129">I punti in NamespaceSpec non accettano la barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="c0c68-129">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="c0c68-130">\\\|Barra rovesciata se necessaria come stringa letterale.</span><span class="sxs-lookup"><span data-stu-id="c0c68-130">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="c0c68-131">Si noti che in tutti i componenti TypeSpec, ad eccezione di AssemblyNameSpec, gli spazi sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="c0c68-131">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="c0c68-132">In AssemblyNameSpec, gli spazi che precedono il separatore ',' sono rilevanti, ma gli spazi dopo il separatore ',' vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="c0c68-132">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="c0c68-133">Le classi reflection, ad esempio <xref:System.Type.FullName%2A?displayProperty=nameWithType>, restituiscono il nome modificato in modo che possa essere usato in una chiamata a <xref:System.Type.GetType%2A>, ad esempio in `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-133">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="c0c68-134">Ad esempio, il nome completo per un tipo potrebbe essere `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-134">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="c0c68-135">Se lo spazio dei nomi fosse `Ozzy.Out+Back`, il segno di addizione dovrebbe essere preceduto da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="c0c68-135">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="c0c68-136">In caso contrario, il parser lo interpreterebbe come separatore di annidamento.</span><span class="sxs-lookup"><span data-stu-id="c0c68-136">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="c0c68-137">Reflection genera questa stringa come `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-137">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="c0c68-138">Specifica dei nomi di assembly</span><span class="sxs-lookup"><span data-stu-id="c0c68-138">Specifying assembly names</span></span>

<span data-ttu-id="c0c68-139">Le informazioni minime necessarie in una specifica di nome di assembly è il nome testuale (IDENTIFIER) dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c0c68-139">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="c0c68-140">È possibile far seguire l'IDENTIFIER da un elenco delimitato da virgole di coppie proprietà/valore, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c0c68-140">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="c0c68-141">La denominazione dell'IDENTIFIER deve seguire le regole di denominazione dei file.</span><span class="sxs-lookup"><span data-stu-id="c0c68-141">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="c0c68-142">La denominazione dell'IDENTIFIER non fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c0c68-142">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="c0c68-143">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c0c68-143">Property name</span></span>|<span data-ttu-id="c0c68-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0c68-144">Description</span></span>|<span data-ttu-id="c0c68-145">Valori consentiti</span><span class="sxs-lookup"><span data-stu-id="c0c68-145">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="c0c68-146">**Version**</span><span class="sxs-lookup"><span data-stu-id="c0c68-146">**Version**</span></span>|<span data-ttu-id="c0c68-147">Numero di versione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="c0c68-147">Assembly version number</span></span>|<span data-ttu-id="c0c68-148">*Major.Minor.Build.Revision*, dove *Major*, *Minor*, *Build* e *Revision* sono numeri interi compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="c0c68-148">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="c0c68-149">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="c0c68-149">**PublicKey**</span></span>|<span data-ttu-id="c0c68-150">Chiave pubblica completa</span><span class="sxs-lookup"><span data-stu-id="c0c68-150">Full public key</span></span>|<span data-ttu-id="c0c68-151">Valore di stringa della chiave pubblica completa in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="c0c68-151">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="c0c68-152">Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.</span><span class="sxs-lookup"><span data-stu-id="c0c68-152">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="c0c68-153">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="c0c68-153">**PublicKeyToken**</span></span>|<span data-ttu-id="c0c68-154">Token di chiave pubblica (hash a 8 byte della chiave pubblica completa)</span><span class="sxs-lookup"><span data-stu-id="c0c68-154">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="c0c68-155">Valore di stringa del token della chiave pubblica in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="c0c68-155">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="c0c68-156">Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.</span><span class="sxs-lookup"><span data-stu-id="c0c68-156">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="c0c68-157">**Impostazioni cultura**</span><span class="sxs-lookup"><span data-stu-id="c0c68-157">**Culture**</span></span>|<span data-ttu-id="c0c68-158">Impostazioni cultura dell'assembly</span><span class="sxs-lookup"><span data-stu-id="c0c68-158">Assembly culture</span></span>|<span data-ttu-id="c0c68-159">Impostazioni cultura dell'assembly in formato RFC 1766 o "neutral" per gli assembly indipendenti dal linguaggio (non satellite).</span><span class="sxs-lookup"><span data-stu-id="c0c68-159">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="c0c68-160">**Impostazione personalizzata**</span><span class="sxs-lookup"><span data-stu-id="c0c68-160">**Custom**</span></span>|<span data-ttu-id="c0c68-161">BLOB (Binary Large Object, Oggetto binario di grandi dimensioni) personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c0c68-161">Custom binary large object (BLOB).</span></span> <span data-ttu-id="c0c68-162">Attualmente viene usato solo in assembly generati dal [generatore di immagini native (Ngen)](../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="c0c68-162">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="c0c68-163">Stringa personalizzata usata dal generatore di immagini native per notificare alla cache di assembly che l'assembly che si sta installando è un'immagine nativa e deve pertanto essere installato nella cache delle immagini native.</span><span class="sxs-lookup"><span data-stu-id="c0c68-163">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="c0c68-164">Nota anche come stringa zap.</span><span class="sxs-lookup"><span data-stu-id="c0c68-164">Also called a zap string.</span></span>|

<span data-ttu-id="c0c68-165">L'esempio seguente illustra un **AssemblyName** per un assembly a nome semplice con le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="c0c68-165">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="c0c68-166">L'esempio seguente illustra un riferimento completo per un assembly con nome sicuro nelle impostazioni cultura "en" (inglese).</span><span class="sxs-lookup"><span data-stu-id="c0c68-166">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="c0c68-167">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che può essere soddisfatto da un assembly con nome sicuro o semplice.</span><span class="sxs-lookup"><span data-stu-id="c0c68-167">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="c0c68-168">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome semplice.</span><span class="sxs-lookup"><span data-stu-id="c0c68-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="c0c68-169">Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="c0c68-169">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="c0c68-170">Specifica di tipi generici</span><span class="sxs-lookup"><span data-stu-id="c0c68-170">Specifying generic types</span></span>

<span data-ttu-id="c0c68-171">SimpleTypeSpec\`NUMERO rappresenta un tipo generico aperto con parametri di tipo generico compresi tra 1 e *n*.</span><span class="sxs-lookup"><span data-stu-id="c0c68-171">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="c0c68-172">Per ottenere, ad esempio, un riferimento all'elenco di tipi generici aperti \<T> o all'elenco di tipi generici chiusi \<String> , usare ``Type.GetType("System.Collections.Generic.List`1")`` per ottenere un riferimento al dizionario di tipo generico \<TKey,TValue> , usare ``Type.GetType("System.Collections.Generic.Dictionary`2")`` .</span><span class="sxs-lookup"><span data-stu-id="c0c68-172">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="c0c68-173">Specifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="c0c68-173">Specifying pointers</span></span>

<span data-ttu-id="c0c68-174">SimpleTypeSpec\* rappresenta un puntatore non gestito.</span><span class="sxs-lookup"><span data-stu-id="c0c68-174">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="c0c68-175">Ad esempio, per ottenere un puntatore per il tipo MyType, usare `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-175">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="c0c68-176">Per ottenere un puntatore a un puntatore per il tipo MyType, usare `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-176">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="c0c68-177">Specifica dei riferimenti</span><span class="sxs-lookup"><span data-stu-id="c0c68-177">Specifying references</span></span>

<span data-ttu-id="c0c68-178">SimpleTypeSpec & rappresenta un riferimento o puntatore gestito.</span><span class="sxs-lookup"><span data-stu-id="c0c68-178">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="c0c68-179">Ad esempio, per ottenere un riferimento per il tipo MyType, usare `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="c0c68-179">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="c0c68-180">Si noti che, a differenza dei puntatori, i riferimenti sono limitati a un solo livello.</span><span class="sxs-lookup"><span data-stu-id="c0c68-180">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="c0c68-181">Specifica delle matrici</span><span class="sxs-lookup"><span data-stu-id="c0c68-181">Specifying arrays</span></span>

<span data-ttu-id="c0c68-182">Nella grammatica BNF, ReflectionEmitDimension si applica solo a definizioni di tipi incomplete recuperate tramite <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0c68-182">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c0c68-183">Le definizioni di tipi incomplete sono oggetti <xref:System.Reflection.Emit.TypeBuilder> costruiti tramite <xref:System.Reflection.Emit?displayProperty=nameWithType> senza chiamare <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0c68-183">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="c0c68-184">ReflectionDimension può essere usato per recuperare qualsiasi definizione di tipo che è stata completata, vale a dire, un tipo che è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="c0c68-184">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="c0c68-185">Le matrici sono accessibili in reflection specificando l'ordine della matrice:</span><span class="sxs-lookup"><span data-stu-id="c0c68-185">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="c0c68-186">`Type.GetType("MyArray[]")` ottiene una matrice unidimensionale con un limite inferiore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="c0c68-186">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="c0c68-187">`Type.GetType("MyArray[*]")` ottiene una matrice unidimensionale con un limite inferiore sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c0c68-187">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="c0c68-188">`Type.GetType("MyArray[][]")` ottiene una matrice di matrice bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="c0c68-188">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="c0c68-189">`Type.GetType("MyArray[*,*]")` e `Type.GetType("MyArray[,]")` ottengono una matrice rettangolare bidimensionale con limiti inferiori sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="c0c68-189">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="c0c68-190">Si noti che dal punto di vista del runtime, `MyArray[] != MyArray[*]`, ma per le matrici multidimensionali, le due notazioni sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c0c68-190">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="c0c68-191">Vale a dire, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` restituisce **true**.</span><span class="sxs-lookup"><span data-stu-id="c0c68-191">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="c0c68-192">Per **ModuleBuilder. GetType**, `MyArray[0..5]` indica una matrice a dimensione singola con dimensione 6, limite inferiore 0.</span><span class="sxs-lookup"><span data-stu-id="c0c68-192">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="c0c68-193">`MyArray[4…]` indica una matrice unidimensionale di dimensioni sconosciute e limite inferiore pari a 4.</span><span class="sxs-lookup"><span data-stu-id="c0c68-193">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0c68-194">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c0c68-194">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c0c68-195">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="c0c68-195">Viewing Type Information</span></span>](viewing-type-information.md)
