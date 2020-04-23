---
title: Tipi incorporati per primitive del linguaggio XAML comuni
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: 3bd486ee66c5f9a32621416638bb7575025f7dee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071836"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a><span data-ttu-id="f35ae-102">Tipi predefiniti per primitive comuni del linguaggio XAMLBuilt-in types for common XAML language primitives</span><span class="sxs-lookup"><span data-stu-id="f35ae-102">Built-in types for common XAML language primitives</span></span>

<span data-ttu-id="f35ae-103">XAML 2009 introduce il supporto del livello di linguaggio XAML per diversi tipi di dati che sono primitive di uso frequente in Common Language Runtime (CLR) e in altri linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f35ae-103">XAML 2009 introduces XAML language-level support for several data types that are frequently used primitives in the common language runtime (CLR) and in other programming languages.</span></span> <span data-ttu-id="f35ae-104">XAML 2009 aggiunge il supporto per queste primitive: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`e `x:Array`</span><span class="sxs-lookup"><span data-stu-id="f35ae-104">XAML 2009 adds support for these primitives: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`, and `x:Array`</span></span>

## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a><span data-ttu-id="f35ae-105">Tecniche precedenti per le primitive di linguaggio nel markup XAML</span><span class="sxs-lookup"><span data-stu-id="f35ae-105">Previous Techniques for Language Primitives in XAML Markup</span></span>

 <span data-ttu-id="f35ae-106">In XAML per le versioni di WPF precedenti era possibile fare riferimento alle primitive del linguaggio CLR eseguendo il mapping dell'assembly e dello spazio dei nomi che contenevano una classe di definizione della primitiva CLR per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f35ae-106">In XAML for previous WPF versions, you could reference the CLR language primitives by mapping the assembly and namespace that contained a CLR primitive definition class for the .NET Framework.</span></span> <span data-ttu-id="f35ae-107">La maggior parte di queste si trovano nell'assembly mscorlib e nello spazio dei nomi <xref:System> .</span><span class="sxs-lookup"><span data-stu-id="f35ae-107">Most of these are in the mscorlib assembly and <xref:System> namespace.</span></span> <span data-ttu-id="f35ae-108">Ad esempio, per usare <xref:System.Int32>era possibile dichiarare il mapping seguente (con un esempio di utilizzo come illustrato di seguito):</span><span class="sxs-lookup"><span data-stu-id="f35ae-108">For example, to use <xref:System.Int32>, you could declare the following mapping (with an example usage shown thereafter):</span></span>

```xaml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Application.Resources>
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>
  </Application.Resources>
</Application>
```

## <a name="xaml-2009-language-primitives"></a><span data-ttu-id="f35ae-109">Primitive del linguaggio XAML 2009</span><span class="sxs-lookup"><span data-stu-id="f35ae-109">XAML 2009 Language Primitives</span></span>

<span data-ttu-id="f35ae-110">Per convenzione, le primitive di linguaggio per XAML e tutti gli altri elementi del linguaggio XAML vengono mostrati con il prefisso `x:` .</span><span class="sxs-lookup"><span data-stu-id="f35ae-110">By convention, the language primitives for XAML and all other XAML language elements are shown, including the `x:` prefix.</span></span> <span data-ttu-id="f35ae-111">Questo è il modo in cui gli elementi del linguaggio XAML vengono in genere usati nel markup reale.</span><span class="sxs-lookup"><span data-stu-id="f35ae-111">This is how XAML language elements are typically used in real-world markup.</span></span> <span data-ttu-id="f35ae-112">Questa convenzione viene seguita nella documentazione concettuale per XAML in WPF e anche nelle specifiche XAML.</span><span class="sxs-lookup"><span data-stu-id="f35ae-112">This convention is followed in the conceptual documentation for XAML in WPF and also in the XAML specification.</span></span>

### <a name="xobject"></a><span data-ttu-id="f35ae-113">x:Object</span><span class="sxs-lookup"><span data-stu-id="f35ae-113">x:Object</span></span>

<span data-ttu-id="f35ae-114">Per il supporto CLR, la primitiva `x:Object` corrisponde a <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-114">For CLR backing, the `x:Object` primitive corresponds to <xref:System.Object>.</span></span>

<span data-ttu-id="f35ae-115">Questa primitiva in genere non viene usata nel markup dell'applicazione, ma può essere utile per alcuni scenari, ad esempio la verifica dell'assegnabilità in un sistema di tipi XAML.</span><span class="sxs-lookup"><span data-stu-id="f35ae-115">This primitive is not typically used in application markup, but might be useful for some scenarios such as checking assignability in a XAML type system.</span></span>

### <a name="xboolean"></a><span data-ttu-id="f35ae-116">x:Boolean</span><span class="sxs-lookup"><span data-stu-id="f35ae-116">x:Boolean</span></span>

<span data-ttu-id="f35ae-117">Per il supporto CLR, la primitiva `x:Boolean` corrisponde a <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-117">For CLR backing, the `x:Boolean` primitive corresponds to <xref:System.Boolean>.</span></span>

<span data-ttu-id="f35ae-118">XAML analizza i valori per `x:Boolean` senza fare distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f35ae-118">XAML parses values for `x:Boolean` as case insensitive.</span></span> <span data-ttu-id="f35ae-119">Tenere presente che `x:Bool` non rappresenta un'alternativa valida.</span><span class="sxs-lookup"><span data-stu-id="f35ae-119">Note that `x:Bool` is not an accepted alternative.</span></span> <span data-ttu-id="f35ae-120">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.17 e 5.4.11.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-120">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.17 and 5.4.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xchar"></a><span data-ttu-id="f35ae-121">x:Char</span><span class="sxs-lookup"><span data-stu-id="f35ae-121">x:Char</span></span>

<span data-ttu-id="f35ae-122">Per il supporto CLR, la primitiva `x:Char` corrisponde a <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-122">For CLR backing, the `x:Char` primitive corresponds to <xref:System.Char>.</span></span>

<span data-ttu-id="f35ae-123">I tipi string e char interagiscono con la codifica globale del file a livello di XML.</span><span class="sxs-lookup"><span data-stu-id="f35ae-123">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="f35ae-124">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.7 e 5.4.1 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-124">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.7 and 5.4.1](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xstring"></a><span data-ttu-id="f35ae-125">x:String</span><span class="sxs-lookup"><span data-stu-id="f35ae-125">x:String</span></span>

<span data-ttu-id="f35ae-126">Per il supporto CLR, la primitiva `x:String` corrisponde a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-126">For CLR backing, the `x:String` primitive corresponds to <xref:System.String>.</span></span>

<span data-ttu-id="f35ae-127">I tipi string e char interagiscono con la codifica globale del file a livello di XML.</span><span class="sxs-lookup"><span data-stu-id="f35ae-127">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="f35ae-128">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.6 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-128">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdecimal"></a><span data-ttu-id="f35ae-129">x:Decimal</span><span class="sxs-lookup"><span data-stu-id="f35ae-129">x:Decimal</span></span>

<span data-ttu-id="f35ae-130">Per il supporto CLR, la primitiva `x:Decimal` corrisponde a <xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-130">For CLR backing, the `x:Decimal` primitive corresponds to <xref:System.Decimal>.</span></span>

<span data-ttu-id="f35ae-131">L'analisi XAML viene eseguita intrinsecamente con `en-US` le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f35ae-131">XAML parsing is inherently done under `en-US` culture.</span></span> <span data-ttu-id="f35ae-132">Con le impostazioni cultura `en-US` , il separatore corretto per i componenti di un numero decimale è sempre un punto (`.`) indipendentemente dalle impostazioni cultura dell'ambiente di sviluppo o dell'eventuale destinazione client in cui XAML viene caricato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f35ae-132">Under `en-US` culture, the correct separator for the components of a decimal is always a period (`.`) regardless of culture settings of the development environment, or of the eventual client target where the XAML is loaded at run time.</span></span>

<span data-ttu-id="f35ae-133">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.14 e 5.4.8.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-133">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.14 and 5.4.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xsingle"></a><span data-ttu-id="f35ae-134">x:Single</span><span class="sxs-lookup"><span data-stu-id="f35ae-134">x:Single</span></span>

<span data-ttu-id="f35ae-135">Per il supporto CLR, la primitiva `x:Single` corrisponde a <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-135">For CLR backing, the `x:Single` primitive corresponds to <xref:System.Single>.</span></span>

<span data-ttu-id="f35ae-136">Oltre ai valori numerici, nella sintassi del testo per `x:Single` è consentito anche l'uso dei token `Infinity`, `-Infinity`e `NaN`.</span><span class="sxs-lookup"><span data-stu-id="f35ae-136">In addition to the numeric values, text syntax for `x:Single` also permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="f35ae-137">Per questi token viene rilevata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f35ae-137">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="f35ae-138">`x:Single` può supportare valori nel formato di notazione scientifico, se il primo carattere nella sintassi del testo è `e` o `E`.</span><span class="sxs-lookup"><span data-stu-id="f35ae-138">`x:Single` can support values in scientific notation form, if the first character in text syntax is `e` or `E`.</span></span>

<span data-ttu-id="f35ae-139">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.8 e 5.4.2 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-139">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.8 and 5.4.2](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdouble"></a><span data-ttu-id="f35ae-140">x:Double</span><span class="sxs-lookup"><span data-stu-id="f35ae-140">x:Double</span></span>

<span data-ttu-id="f35ae-141">Per il supporto CLR, la primitiva `x:Double` corrisponde a <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-141">For CLR backing, the `x:Double` primitive corresponds to <xref:System.Double>.</span></span>

<span data-ttu-id="f35ae-142">Oltre ai valori numerici, nella sintassi del testo per `x:Double` è consentito l'uso dei token `Infinity`, `-Infinity`e `NaN`.</span><span class="sxs-lookup"><span data-stu-id="f35ae-142">In addition to the numeric values, text syntax for `x:Double` permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="f35ae-143">Per questi token viene rilevata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f35ae-143">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="f35ae-144">`x:Double` può supportare valori nel formato di notazione scientifico.</span><span class="sxs-lookup"><span data-stu-id="f35ae-144">`x:Double` can support values in scientific notation form.</span></span> <span data-ttu-id="f35ae-145">Utilizzare il carattere `e` o `E` per introdurre la parte dell'esponente.</span><span class="sxs-lookup"><span data-stu-id="f35ae-145">Use the character `e` or `E` to introduce the exponent portion.</span></span>

<span data-ttu-id="f35ae-146">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.9 e 5.4.3 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-146">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.9 and 5.4.3](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint16"></a><span data-ttu-id="f35ae-147">x:Int16</span><span class="sxs-lookup"><span data-stu-id="f35ae-147">x:Int16</span></span>

<span data-ttu-id="f35ae-148">Per il supporto CLR, la primitiva `x:Int16` corrisponde a <xref:System.Int16> e `x:Int16` viene considerato con segno.</span><span class="sxs-lookup"><span data-stu-id="f35ae-148">For CLR backing, the `x:Int16` primitive corresponds to <xref:System.Int16> and `x:Int16` is treated as signed.</span></span> <span data-ttu-id="f35ae-149">In XAML l'assenza di un segno più (`+`) nella sintassi del testo indica implicitamente un valore con segno positivo.</span><span class="sxs-lookup"><span data-stu-id="f35ae-149">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="f35ae-150">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.11 e 5.4.5.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-150">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.11 and 5.4.5](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint32"></a><span data-ttu-id="f35ae-151">x:Int32</span><span class="sxs-lookup"><span data-stu-id="f35ae-151">x:Int32</span></span>

<span data-ttu-id="f35ae-152">Per il supporto CLR, la primitiva `x:Int32` corrisponde a <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-152">For CLR backing, the `x:Int32` primitive corresponds to <xref:System.Int32>.</span></span> <span data-ttu-id="f35ae-153">`x:Int32` viene considerato un valore con segno.</span><span class="sxs-lookup"><span data-stu-id="f35ae-153">`x:Int32` is treated as signed.</span></span> <span data-ttu-id="f35ae-154">In XAML l'assenza di un segno più (`+`) nella sintassi del testo indica implicitamente un valore con segno positivo.</span><span class="sxs-lookup"><span data-stu-id="f35ae-154">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="f35ae-155">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.12 e 5.4.6.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-155">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.12 and 5.4.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint64"></a><span data-ttu-id="f35ae-156">x:Int64</span><span class="sxs-lookup"><span data-stu-id="f35ae-156">x:Int64</span></span>

<span data-ttu-id="f35ae-157">Per il supporto CLR, la primitiva `x:Int64` corrisponde a <xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-157">For CLR backing, the `x:Int64` primitive corresponds to <xref:System.Int64>.</span></span> <span data-ttu-id="f35ae-158">`x:Int64` viene considerato un valore con segno.</span><span class="sxs-lookup"><span data-stu-id="f35ae-158">`x:Int64` is treated as signed.</span></span> <span data-ttu-id="f35ae-159">In XAML l'assenza di un segno più (`+`) nella sintassi del testo indica implicitamente un valore con segno positivo.</span><span class="sxs-lookup"><span data-stu-id="f35ae-159">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="f35ae-160">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.13 e 5.4.7.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-160">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.13 and 5.4.7](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xtimespan"></a><span data-ttu-id="f35ae-161">x:TimeSpan</span><span class="sxs-lookup"><span data-stu-id="f35ae-161">x:TimeSpan</span></span>

<span data-ttu-id="f35ae-162">Per il supporto CLR, la primitiva `x:TimeSpan` corrisponde a <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-162">For CLR backing, the `x:TimeSpan` primitive corresponds to <xref:System.TimeSpan>.</span></span>

<span data-ttu-id="f35ae-163">L'analisi XAML per il formato della `en-US` data e dell'ora viene eseguita intrinsecamente con le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f35ae-163">XAML parsing for time-date format is inherently done under `en-US` culture.</span></span>

<span data-ttu-id="f35ae-164">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.16 e 5.4.10.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-164">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.16 and 5.4.10](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xuri"></a><span data-ttu-id="f35ae-165">x:Uri</span><span class="sxs-lookup"><span data-stu-id="f35ae-165">x:Uri</span></span>

<span data-ttu-id="f35ae-166">Per il supporto CLR, la primitiva `x:Uri` corrisponde a <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-166">For CLR backing, the `x:Uri` primitive corresponds to <xref:System.Uri>.</span></span>

<span data-ttu-id="f35ae-167">La verifica dei protocolli non fa parte della definizione XAML per `x:Uri`.</span><span class="sxs-lookup"><span data-stu-id="f35ae-167">Checking for protocols is not part of the XAML definition for `x:Uri`.</span></span>

<span data-ttu-id="f35ae-168">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni MS-XAML\] 5.2.15 e 5.4.9.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-168">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.15 and 5.4.9](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xbyte"></a><span data-ttu-id="f35ae-169">x:Byte</span><span class="sxs-lookup"><span data-stu-id="f35ae-169">x:Byte</span></span>

<span data-ttu-id="f35ae-170">Per il supporto CLR, la primitiva `x:Byte` corrisponde a <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-170">For CLR backing, the `x:Byte` primitive corresponds to <xref:System.Byte>.</span></span> <span data-ttu-id="f35ae-171"><xref:System.Byte>  /  A `x:Byte` viene considerato come unsigned.</span><span class="sxs-lookup"><span data-stu-id="f35ae-171">A <xref:System.Byte> / `x:Byte` is treated as unsigned.</span></span>

<span data-ttu-id="f35ae-172">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.10 e 5.4.4. di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-172">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.10 and 5.4.4](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xarray"></a><span data-ttu-id="f35ae-173">x:Array</span><span class="sxs-lookup"><span data-stu-id="f35ae-173">x:Array</span></span>

<span data-ttu-id="f35ae-174">Per il supporto CLR, la primitiva `x:Array` corrisponde a <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-174">For CLR backing, the `x:Array` primitive corresponds to <xref:System.Array>.</span></span>

<span data-ttu-id="f35ae-175">In XAML 2006 è possibile definire una matrice utilizzando una sintassi dell'estensione di markup, mentre la sintassi di XAML 2009 è una primitiva definita dal linguaggio che non richiede l'accesso a un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="f35ae-175">You can define an array in XAML 2006  by using a markup extension syntax; however, the XAML 2009 syntax is a language-defined primitive that does not require accessing a markup extension.</span></span> <span data-ttu-id="f35ae-176">Per ulteriori informazioni sul supporto di XAML 2006, vedere [x:Array Markup Extension](xarray-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="f35ae-176">For more information about XAML 2006 support, see [x:Array Markup Extension](xarray-markup-extension.md).</span></span>

<span data-ttu-id="f35ae-177">Per la definizione della specifica del linguaggio XAML, vedere [ \[Sezioni 5.2.18 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="f35ae-177">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.18](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="wpf-support"></a><span data-ttu-id="f35ae-178">Supporto WPF</span><span class="sxs-lookup"><span data-stu-id="f35ae-178">WPF Support</span></span>

<span data-ttu-id="f35ae-179">In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup.</span><span class="sxs-lookup"><span data-stu-id="f35ae-179">In WPF, you can use XAML 2009 features but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="f35ae-180">Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="f35ae-180">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="f35ae-181">Un scenario in cui è possibile usare le funzionalità di XAML 2009 con WPF consiste nella creazione di XAML separato e nel successivo caricamento in un runtime di WPF e in un oggetto grafico con <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f35ae-181">A scenario where you can use XAML 2009 features together with WPF is if you author loose XAML and you then load that XAML into a WPF runtime and object graph with <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f35ae-182">L'oggetto <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> di WPF e il relativo metodo <xref:System.Windows.Markup.XamlReader.Load%2A> possono elaborare parole chiave e funzionalità del linguaggio XAML 2009 in una rappresentazione dell'oggetto grafico valida.</span><span class="sxs-lookup"><span data-stu-id="f35ae-182">The WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and its <xref:System.Windows.Markup.XamlReader.Load%2A> can process XAML 2009 language keywords and features into a valid object graph representation.</span></span>
