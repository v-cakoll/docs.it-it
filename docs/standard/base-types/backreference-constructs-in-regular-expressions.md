---
title: Costrutti di backreference nelle espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2ec92933bdf123412a3d489fc493d76c4a0dc0d0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="4def1-102">Costrutti di backreference nelle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="4def1-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="4def1-103">I backreference sono uno strumento utile per identificare un carattere ripetuto o una sottostringa all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="4def1-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="4def1-104">Se la stringa di input contiene ad esempio più occorrenze di una sottostringa arbitraria, è possibile trovare la prima occorrenza con un gruppo di acquisizione e usare un backreference per trovare le occorrenze successive della sottostringa.</span><span class="sxs-lookup"><span data-stu-id="4def1-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4def1-105">Per fare riferimento a gruppi di acquisizione denominati e numerati in stringhe sostitutive, si usa una sintassi separata.</span><span class="sxs-lookup"><span data-stu-id="4def1-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="4def1-106">Per altre informazioni, vedere [Substitutions](substitutions-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4def1-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="4def1-107">.NET definisce elementi di linguaggio separati per fare riferimento a gruppi di acquisizione denominati e numerati.</span><span class="sxs-lookup"><span data-stu-id="4def1-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="4def1-108">Per altre informazioni sui gruppi di acquisizione, vedere [Costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4def1-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="4def1-109">Backreference numerati</span><span class="sxs-lookup"><span data-stu-id="4def1-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="4def1-110">Nei backreference numerati si usa la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4def1-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="4def1-111">`\` *numero*</span><span class="sxs-lookup"><span data-stu-id="4def1-111">`\` *number*</span></span>  
  
 <span data-ttu-id="4def1-112">dove *numero* è la posizione corretta del gruppo di acquisizione nell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="4def1-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="4def1-113">Ad esempio, `\4` corrisponde al contenuto del quarto gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="4def1-114">Se nel modello di espressione regolare *numero* non è definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="4def1-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="4def1-115">Ad esempio, l'espressione regolare `\b(\w+)\s\1` è valida, poiché `(\w+)` è il primo e l'unico gruppo di acquisizione nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="4def1-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="4def1-116">D'altra parte, `\b(\w+)\s\2` non è un'espressione valida e genera un'eccezione di argomento, perché non esistono gruppi di acquisizione numerati `\2`.</span><span class="sxs-lookup"><span data-stu-id="4def1-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="4def1-117">Si noti l'ambiguità tra i codici di escape ottale, ad esempio `\16`, e i backreference `\`*numero* che usano la stessa notazione.</span><span class="sxs-lookup"><span data-stu-id="4def1-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="4def1-118">Questa ambiguità viene risolta nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4def1-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="4def1-119">Le espressioni da `\1` a `\9` vengono sempre interpretate come backreference e non come codici ottali.</span><span class="sxs-lookup"><span data-stu-id="4def1-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="4def1-120">Se la prima cifra di un'espressione composta da più cifre è 8 o 9, ad esempio `\80` o `\91`, l'espressione viene interpretata come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="4def1-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="4def1-121">Le espressioni con numerazione a partire da `\10` vengono considerate backreference se esiste un backreference a tale numero; in caso contrario, vengono interpretate come codici ottali.</span><span class="sxs-lookup"><span data-stu-id="4def1-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="4def1-122">Se l'espressione regolare contiene un backreference a un numero di gruppo non definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="4def1-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="4def1-123">Se il problema è dovuto all'ambiguità, è possibile usare la notazione `\k<`*nome*`>` che, non essendo ambigua, non può essere confusa con codici di caratteri ottali.</span><span class="sxs-lookup"><span data-stu-id="4def1-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="4def1-124">Analogamente, i codici esadecimale come `\xdd` non sono ambigui e non possono essere confusi con backreference.</span><span class="sxs-lookup"><span data-stu-id="4def1-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="4def1-125">L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="4def1-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="4def1-126">Viene definita un'espressione regolare `(\w)\1` costituita dagli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4def1-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="4def1-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4def1-127">Element</span></span>|<span data-ttu-id="4def1-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4def1-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="4def1-129">Trova la corrispondenza di un carattere alfanumerico e la assegna al primo gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="4def1-130">Trova la corrispondenza del carattere successivo, uguale al valore del primo gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="4def1-131">Backreference denominati</span><span class="sxs-lookup"><span data-stu-id="4def1-131">Named Backreferences</span></span>  
 <span data-ttu-id="4def1-132">Per definire un backreference denominato, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4def1-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="4def1-133">`\k<` *nome* `>`</span><span class="sxs-lookup"><span data-stu-id="4def1-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="4def1-134">oppure:</span><span class="sxs-lookup"><span data-stu-id="4def1-134">or:</span></span>  
  
 <span data-ttu-id="4def1-135">`\k'` *name* `'`</span><span class="sxs-lookup"><span data-stu-id="4def1-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="4def1-136">dove *nome* è il nome di un gruppo di acquisizione definito nel modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="4def1-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="4def1-137">Se nel modello di espressione regolare *nome* non è definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="4def1-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="4def1-138">L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="4def1-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="4def1-139">Viene definita un'espressione regolare `(?<char>\w)\k<char>` costituita dagli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4def1-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="4def1-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="4def1-140">Element</span></span>|<span data-ttu-id="4def1-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4def1-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="4def1-142">Trova la corrispondenza di un carattere alfanumerico e la assegna a un gruppo di acquisizione denominato `char`.</span><span class="sxs-lookup"><span data-stu-id="4def1-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="4def1-143">Trova la corrispondenza del carattere successivo, uguale al valore del gruppo di acquisizione denominato `char`.</span><span class="sxs-lookup"><span data-stu-id="4def1-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="4def1-144">Si noti che *nome* può anche essere la rappresentazione di stringa di un numero.</span><span class="sxs-lookup"><span data-stu-id="4def1-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="4def1-145">Nell'esempio seguente viene usata l'espressione regolare `(?<2>\w)\k<2>` per trovare caratteri alfanumerici doppi all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="4def1-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="4def1-146">Corrispondenza dei backreference</span><span class="sxs-lookup"><span data-stu-id="4def1-146">What Backreferences Match</span></span>  
 <span data-ttu-id="4def1-147">Un backreference fa riferimento alla definizione più recente di un gruppo, vale a dire alla definizione all'estrema sinistra, in caso di corrispondenza da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="4def1-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="4def1-148">Quando un gruppo esegue più acquisizioni, un backreference fa riferimento all'acquisizione più recente.</span><span class="sxs-lookup"><span data-stu-id="4def1-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="4def1-149">L'esempio seguente include un modello di espressione regolare `(?<1>a)(?<1>\1b)*`, che ridefinisce il gruppo denominato \1.</span><span class="sxs-lookup"><span data-stu-id="4def1-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="4def1-150">Nella tabella seguente sono descritti i modelli di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="4def1-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="4def1-151">Modello</span><span class="sxs-lookup"><span data-stu-id="4def1-151">Pattern</span></span>|<span data-ttu-id="4def1-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4def1-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="4def1-153">Trova la corrispondenza del carattere "a" e assegna il risultato al gruppo di acquisizione denominato `1`.</span><span class="sxs-lookup"><span data-stu-id="4def1-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="4def1-154">Trova la corrispondenza dell'occorrenza 0 o 1 del gruppo denominato `1` con una "b" e assegna il risultato al gruppo di acquisizione denominato `1`.</span><span class="sxs-lookup"><span data-stu-id="4def1-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="4def1-155">Confrontando l'espressione regolare con la stringa di input ("aababb"), il motore delle espressioni regolari esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4def1-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="4def1-156">Parte dall'inizio della stringa e trova una corrispondenza per "a" con l'espressione `(?<1>a)`.</span><span class="sxs-lookup"><span data-stu-id="4def1-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="4def1-157">Il valore del `1` gruppo è ora "a".</span><span class="sxs-lookup"><span data-stu-id="4def1-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="4def1-158">Passa al secondo carattere e trova una corrispondenza per la stringa "ab" con l'espressione `\1b` o "ab".</span><span class="sxs-lookup"><span data-stu-id="4def1-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="4def1-159">Assegna il risultato "ab" a `\1`.</span><span class="sxs-lookup"><span data-stu-id="4def1-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="4def1-160">Passa al quarto carattere.</span><span class="sxs-lookup"><span data-stu-id="4def1-160">It advances to the fourth character.</span></span> <span data-ttu-id="4def1-161">Per l'espressione `(?<1>\1b)` la corrispondenza individuata deve essere zero o più volte, ai fini di una corrispondenza corretta della stringa "abb" con l'espressione `\1b`.</span><span class="sxs-lookup"><span data-stu-id="4def1-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="4def1-162">Assegna il risultato "abb" nuovamente a `\1`.</span><span class="sxs-lookup"><span data-stu-id="4def1-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="4def1-163">In questo esempio `*` è un quantificatore di cicli, vale a dire che viene eseguito ripetutamente finché il motore delle espressioni regolari non trova una corrispondenza con il modello che definisce.</span><span class="sxs-lookup"><span data-stu-id="4def1-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="4def1-164">I quantificatori di cicli non cancellano le definizioni di gruppi.</span><span class="sxs-lookup"><span data-stu-id="4def1-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="4def1-165">Se un gruppo non ha acquisito alcuna sottostringa, un backreference a tale gruppo risulterà non definito e non troverà mai corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="4def1-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="4def1-166">Questo comportamento è illustrato dal modello delle espressioni regolari `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, definito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4def1-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="4def1-167">Modello</span><span class="sxs-lookup"><span data-stu-id="4def1-167">Pattern</span></span>|<span data-ttu-id="4def1-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4def1-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="4def1-169">Inizia la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="4def1-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="4def1-170">Trova la corrispondenza di due maiuscole.</span><span class="sxs-lookup"><span data-stu-id="4def1-170">Match two uppercase letters.</span></span> <span data-ttu-id="4def1-171">Equivale al primo gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="4def1-172">Trova la corrispondenza di zero o di una occorrenza di due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="4def1-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="4def1-173">Equivale al secondo gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="4def1-174">Trova la corrispondenza di due maiuscole.</span><span class="sxs-lookup"><span data-stu-id="4def1-174">Match two uppercase letters.</span></span> <span data-ttu-id="4def1-175">Equivale al terzo gruppo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="4def1-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="4def1-176">Termina la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="4def1-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="4def1-177">Una stringa di input può corrispondere a questa espressione regolare, anche se le due cifre decimali definite dal secondo gruppo di acquisizione non sono presenti.</span><span class="sxs-lookup"><span data-stu-id="4def1-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="4def1-178">L'esempio seguente illustra che, nonostante una corrispondenza corretta, viene individuato un gruppo di acquisizione vuoto tra due gruppi di acquisizione con corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="4def1-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4def1-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4def1-179">See Also</span></span>  
 [<span data-ttu-id="4def1-180">Linguaggio di espressioni regolari - Riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="4def1-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
