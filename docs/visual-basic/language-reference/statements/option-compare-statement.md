---
title: Option Compare (istruzione) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
dev_langs:
- VB
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword
- binary comparison
- strings [Visual Basic], returning from functions
- binary comparison, Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword, Option Compare statement
- Binary keyword, Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 00618cd914c06b896d68b4074464af866f747895
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="option-compare-statement"></a><span data-ttu-id="566a9-102">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="566a9-102">Option Compare Statement</span></span>
<span data-ttu-id="566a9-103">Dichiara il metodo di confronto predefinito da usare durante il confronto dei dati di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="566a9-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="566a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="566a9-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="566a9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="566a9-105">Parts</span></span>  
  
|<span data-ttu-id="566a9-106">Termine</span><span class="sxs-lookup"><span data-stu-id="566a9-106">Term</span></span>|<span data-ttu-id="566a9-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="566a9-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="566a9-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="566a9-108">Optional.</span></span> <span data-ttu-id="566a9-109">Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="566a9-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="566a9-110">Questo tipo di confronto è particolarmente utile se le stringhe possono contenere caratteri che non devono essere interpretati come testo.</span><span class="sxs-lookup"><span data-stu-id="566a9-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="566a9-111">In questo caso, non è consigliabile consentire che il confronto sia falsato da equivalenze alfabetiche, ad esempio dalla mancata distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="566a9-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="566a9-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="566a9-112">Optional.</span></span> <span data-ttu-id="566a9-113">Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento testuale senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="566a9-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="566a9-114">Questo tipo di confronto è utile se le stringhe contengono tutti caratteri di testo e si vuole confrontarle prendendo in considerazione le equivalenze alfabetiche, quali la mancata distinzione tra maiuscole e minuscole e le lettere strettamente correlate.</span><span class="sxs-lookup"><span data-stu-id="566a9-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="566a9-115">Ad esempio, è possibile considerare le lettere `A` e `a` equivalenti e fare in modo che le lettere `Ä` e `ä` precedano `B` e `b`.</span><span class="sxs-lookup"><span data-stu-id="566a9-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="566a9-116">Note</span><span class="sxs-lookup"><span data-stu-id="566a9-116">Remarks</span></span>  
 <span data-ttu-id="566a9-117">Se usato, è necessario includere l'istruzione `Option Compare` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="566a9-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="566a9-118">L'istruzione `Option Compare` specifica il metodo di confronto tra stringhe (`Binary` o `Text`).</span><span class="sxs-lookup"><span data-stu-id="566a9-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="566a9-119">Il metodo di confronto del testo predefinito è `Binary`.</span><span class="sxs-lookup"><span data-stu-id="566a9-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="566a9-120">Un confronto `Binary` confronta il valore numerico Unicode di ogni carattere in ciascuna stringa.</span><span class="sxs-lookup"><span data-stu-id="566a9-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="566a9-121">Un confronto `Text` confronta ogni carattere Unicode in base al relativo significato lessicale nelle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="566a9-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="566a9-122">Il criterio di ordinamento di Microsoft Windows è determinato dalla tabella codici.</span><span class="sxs-lookup"><span data-stu-id="566a9-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="566a9-123">Per altre informazioni, vedere [Tabelle codici](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="566a9-123">For more information, see [Code Pages](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="566a9-124">Nell'esempio seguente i caratteri nella tabella codici (ANSI 1252) per le lingue inglese ed europee vengono ordinati usando `Option Compare Binary`, che determina un tipico ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="566a9-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="566a9-125">Se gli stessi caratteri nella stessa tabella codici venissero ordinati con `Option Compare Text`, si otterrebbe il seguente ordinamento testuale.</span><span class="sxs-lookup"><span data-stu-id="566a9-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="566a9-126">Quando non è presente un'istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="566a9-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="566a9-127">Se il codice sorgente non contiene un `Option Compare` istruzione, il **Option Compare** impostazione per il [pagina Compila, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="566a9-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="566a9-128">Se si utilizza il compilatore della riga di comando, l'impostazione specificata per il [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) viene utilizzata l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="566a9-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="566a9-129">Per impostare Option Compare nell'IDE</span><span class="sxs-lookup"><span data-stu-id="566a9-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="566a9-130">In **Esplora**, selezionare un progetto.</span><span class="sxs-lookup"><span data-stu-id="566a9-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="566a9-131">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="566a9-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="566a9-132">Per ulteriori informazioni, vedere [NIB: gestione di proprietà del progetto con Progettazione](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="566a9-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="566a9-133">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="566a9-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="566a9-134">Impostare il valore di **Option Compare** casella.</span><span class="sxs-lookup"><span data-stu-id="566a9-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="566a9-135">Quando si crea un progetto, il **Option Compare** impostazione per il **compilare** scheda è impostata sul **Option Compare** impostazione nel **opzioni** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="566a9-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="566a9-136">Per modificare questa impostazione, scegliere il **strumenti** menu, fare clic su **opzioni**.</span><span class="sxs-lookup"><span data-stu-id="566a9-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="566a9-137">Nel **opzioni** finestra di dialogo espandere **progetti e soluzioni**, quindi fare clic su **impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="566a9-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="566a9-138">L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è **binario**.</span><span class="sxs-lookup"><span data-stu-id="566a9-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="566a9-139">Per impostare Option Compare sulla riga di comando</span><span class="sxs-lookup"><span data-stu-id="566a9-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="566a9-140">Includere il [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) opzione del compilatore di **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="566a9-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="566a9-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="566a9-141">Example</span></span>  
 <span data-ttu-id="566a9-142">Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il confronto binario come metodo predefinito per il confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="566a9-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="566a9-143">Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Binary` e inserirlo all'inizio del file di origine.</span><span class="sxs-lookup"><span data-stu-id="566a9-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="566a9-144">[!code-vb[N. VbVbalrStatements&45;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="566a9-144">[!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="566a9-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="566a9-145">Example</span></span>  
 <span data-ttu-id="566a9-146">Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il criterio di ordinamento del testo senza distinzione tra maiuscole e minuscole come metodo predefinito per il confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="566a9-146">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="566a9-147">Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Text` e inserirlo all'inizio del file di origine.</span><span class="sxs-lookup"><span data-stu-id="566a9-147">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="566a9-148">[!code-vb[VbVbalrStatements n.&46;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="566a9-148">[!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="566a9-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="566a9-149">See Also</span></span>  
 <span data-ttu-id="566a9-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></xref:Microsoft.VisualBasic.Strings.InStr%2A></span><span class="sxs-lookup"><span data-stu-id="566a9-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></span></span>   
 <span data-ttu-id="566a9-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span><span class="sxs-lookup"><span data-stu-id="566a9-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span></span>   
 <span data-ttu-id="566a9-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></xref:Microsoft.VisualBasic.Strings.Replace%2A></span><span class="sxs-lookup"><span data-stu-id="566a9-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></span></span>   
 <span data-ttu-id="566a9-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="566a9-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="566a9-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></xref:Microsoft.VisualBasic.Strings.StrComp%2A></span><span class="sxs-lookup"><span data-stu-id="566a9-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></span></span>   
<span data-ttu-id="566a9-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="566a9-156"> [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-156"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="566a9-157"> [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-157"> [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="566a9-158"> [LIKE (operatore)](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-158"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="566a9-159"> [Funzioni stringa](../../../visual-basic/language-reference/functions/string-functions.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-159"> [String Functions](../../../visual-basic/language-reference/functions/string-functions.md) </span></span>  
<span data-ttu-id="566a9-160"> [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="566a9-160"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="566a9-161"> [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="566a9-161"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
