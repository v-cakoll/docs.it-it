---
title: '@ (Riferimenti per C#)'
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08e3da6aaeee037d7272ea8cddc4382a436b683b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a><span data-ttu-id="189be-102">@ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="189be-102">@ (C# Reference)</span></span>

<span data-ttu-id="189be-103">Il carattere speciale `@` funge da identificatore verbatim.</span><span class="sxs-lookup"><span data-stu-id="189be-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="189be-104">Può essere usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="189be-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="189be-105">Per abilitare le parole chiave di C# da usare come identificatori.</span><span class="sxs-lookup"><span data-stu-id="189be-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="189be-106">Il carattere `@` precede un elemento di codice che il compilatore deve interpretare come identificatore piuttosto che come parola chiave di C#.</span><span class="sxs-lookup"><span data-stu-id="189be-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="189be-107">Nell'esempio seguente il carattere `@` viene usato per definire un identificatore denominato `for` che verrà usato in un ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="189be-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   <span data-ttu-id="189be-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="189be-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span></span>

1. <span data-ttu-id="189be-109">Per indicare che un valore letterale stringa deve essere interpretato come verbatim.</span><span class="sxs-lookup"><span data-stu-id="189be-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="189be-110">Il carattere `@` in questa istanza definisce un *valore letterale stringa verbatim*.</span><span class="sxs-lookup"><span data-stu-id="189be-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="189be-111">Le sequenze di escape semplici, ad esempio `"\\"` per una barra rovesciata, le sequenze di escape esadecimali, ad esempio `"\x0041"` per una A maiuscola, le sequenze di escape Unicode, ad esempio `"\u0041"` per una A maiuscola, vengono interpretate letteralmente.</span><span class="sxs-lookup"><span data-stu-id="189be-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A, and Unicode escape sequences, such as `"\u0041"` for an uppercase A, are interpreted literally.</span></span> <span data-ttu-id="189be-112">Solo una sequenza di escape per le virgolette doppie (`""`) non viene interpretata letteralmente e produce una virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="189be-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="189be-113">Nell'esempio seguente vengono definiti due percorsi di file identici, uno usando un valore letterale stringa normale e l'altro usando un valore letterale stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="189be-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="189be-114">Questo è uno degli usi più comuni dei valori letterali stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="189be-114">This is one of the more common uses of verbatim string literals.</span></span>

   <span data-ttu-id="189be-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="189be-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span></span>

   <span data-ttu-id="189be-116">Nell'esempio seguente viene illustrato l'effetto della definizione di un valore letterale stringa normale e di un valore letterale stringa verbatim che contengono le sequenze di caratteri identiche.</span><span class="sxs-lookup"><span data-stu-id="189be-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   <span data-ttu-id="189be-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="189be-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span></span>

1. <span data-ttu-id="189be-118">Per consentire al compilatore di distinguere tra gli attributi in caso di conflitto di denominazione.</span><span class="sxs-lookup"><span data-stu-id="189be-118">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="189be-119">Un attributo è un tipo che deriva da @System.Attribute.</span><span class="sxs-lookup"><span data-stu-id="189be-119">An attribute is a type that derives from @System.Attribute.</span></span> <span data-ttu-id="189be-120">Il nome del relativo tipo in genere include il suffisso **Attribute**, anche se il compilatore non applica questa convenzione.</span><span class="sxs-lookup"><span data-stu-id="189be-120">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="189be-121">È possibile fare riferimento all'attributo nel codice usando il nome completo del tipo, ad esempio `[InfoAttribute]`, o il nome abbreviato, ad esempio, `[Info]`.</span><span class="sxs-lookup"><span data-stu-id="189be-121">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="189be-122">Tuttavia, si verifica un conflitto di denominazione se due nomi di tipo di attributo abbreviati sono identici e se un nome di tipo include il suffisso **Attribute** e l'altro no.</span><span class="sxs-lookup"><span data-stu-id="189be-122">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="189be-123">Ad esempio, il codice seguente non viene compilato perché il compilatore non è in grado di determinare se l'attributo `Info` o `InfoAttribute` viene applicato al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="189be-123">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Main` method.</span></span>

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   <span data-ttu-id="189be-124">Se si usa l'identificatore verbatim per identificare l'attributo `Info`, l'esempio viene compilato correttamente.</span><span class="sxs-lookup"><span data-stu-id="189be-124">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   <span data-ttu-id="189be-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="189be-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span></span>

## <a name="see-also"></a><span data-ttu-id="189be-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="189be-126">See Also</span></span>  
 <span data-ttu-id="189be-127">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="189be-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="189be-128">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="189be-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="189be-129">[C# Special Characters](../../../csharp/language-reference/tokens/index.md) (Caratteri speciali di C#)</span><span class="sxs-lookup"><span data-stu-id="189be-129">[C# Special Characters](../../../csharp/language-reference/tokens/index.md)</span></span>

