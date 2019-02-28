---
title: Istruzione Option Compare (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
ms.openlocfilehash: c90e07afb1515b50ad6e2fd2a1bbe42f6da5fa95
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968140"
---
# <a name="option-compare-statement"></a><span data-ttu-id="6e13f-102">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="6e13f-102">Option Compare Statement</span></span>
<span data-ttu-id="6e13f-103">Dichiara il metodo di confronto predefinito da usare durante il confronto dei dati di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="6e13f-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e13f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e13f-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="6e13f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6e13f-105">Parts</span></span>  
  
|<span data-ttu-id="6e13f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6e13f-106">Term</span></span>|<span data-ttu-id="6e13f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6e13f-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="6e13f-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e13f-108">Optional.</span></span> <span data-ttu-id="6e13f-109">Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="6e13f-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="6e13f-110">Questo tipo di confronto è particolarmente utile se le stringhe possono contenere caratteri che non devono essere interpretati come testo.</span><span class="sxs-lookup"><span data-stu-id="6e13f-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="6e13f-111">In questo caso, non è consigliabile consentire che il confronto sia falsato da equivalenze alfabetiche, ad esempio dalla mancata distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6e13f-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="6e13f-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6e13f-112">Optional.</span></span> <span data-ttu-id="6e13f-113">Consente di eseguire confronti tra stringhe basati su un criterio di ordinamento testuale senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="6e13f-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="6e13f-114">Questo tipo di confronto è utile se le stringhe contengono tutti caratteri di testo e si vuole confrontarle prendendo in considerazione le equivalenze alfabetiche, quali la mancata distinzione tra maiuscole e minuscole e le lettere strettamente correlate.</span><span class="sxs-lookup"><span data-stu-id="6e13f-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="6e13f-115">Ad esempio, è possibile considerare le lettere `A` e `a` equivalenti e fare in modo che le lettere `Ä` e `ä` precedano `B` e `b`.</span><span class="sxs-lookup"><span data-stu-id="6e13f-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e13f-116">Note</span><span class="sxs-lookup"><span data-stu-id="6e13f-116">Remarks</span></span>  
 <span data-ttu-id="6e13f-117">Se usato, è necessario includere l'istruzione `Option Compare` in un file prima di tutte le altre istruzioni del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6e13f-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="6e13f-118">L'istruzione `Option Compare` specifica il metodo di confronto tra stringhe (`Binary` o `Text`).</span><span class="sxs-lookup"><span data-stu-id="6e13f-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="6e13f-119">Il metodo di confronto del testo predefinito è `Binary`.</span><span class="sxs-lookup"><span data-stu-id="6e13f-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="6e13f-120">Un confronto `Binary` confronta il valore numerico Unicode di ogni carattere in ciascuna stringa.</span><span class="sxs-lookup"><span data-stu-id="6e13f-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="6e13f-121">Un confronto `Text` confronta ogni carattere Unicode in base al relativo significato lessicale nelle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="6e13f-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="6e13f-122">Il criterio di ordinamento di Microsoft Windows è determinato dalla tabella codici.</span><span class="sxs-lookup"><span data-stu-id="6e13f-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="6e13f-123">Per altre informazioni, vedere [Tabelle codici](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="6e13f-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="6e13f-124">Nell'esempio seguente i caratteri nella tabella codici (ANSI 1252) per le lingue inglese ed europee vengono ordinati usando `Option Compare Binary`, che determina un tipico ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="6e13f-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="6e13f-125">Se gli stessi caratteri nella stessa tabella codici venissero ordinati con `Option Compare Text`, si otterrebbe il seguente ordinamento testuale.</span><span class="sxs-lookup"><span data-stu-id="6e13f-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="6e13f-126">Quando non è presente un'istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="6e13f-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="6e13f-127">Se il codice sorgente non contiene un `Option Compare` istruzione, il **Option Compare** impostazione il [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene usato.</span><span class="sxs-lookup"><span data-stu-id="6e13f-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="6e13f-128">Se si usa il compilatore della riga di comando, l'impostazione specificata per il [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) viene utilizzata l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6e13f-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="6e13f-129">Per impostare Option Compare nell'IDE</span><span class="sxs-lookup"><span data-stu-id="6e13f-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="6e13f-130">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="6e13f-131">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-131">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6e13f-132">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-132">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="6e13f-133">Impostare il valore di **Option Compare** casella.</span><span class="sxs-lookup"><span data-stu-id="6e13f-133">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="6e13f-134">Quando si crea un progetto, il **Option Compare** impostazione nel **compilare** scheda è impostata sul **Option Compare** impostazione nel **opzioni** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6e13f-134">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="6e13f-135">Per modificare questa impostazione, scegliere il **degli strumenti** menu, fare clic su **opzioni**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-135">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="6e13f-136">Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-136">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="6e13f-137">L'impostazione predefinita iniziale in **le impostazioni predefinite di Visual Basic** viene **binario**.</span><span class="sxs-lookup"><span data-stu-id="6e13f-137">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="6e13f-138">Per impostare Option Compare sulla riga di comando</span><span class="sxs-lookup"><span data-stu-id="6e13f-138">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="6e13f-139">Includere il [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) opzione del compilatore nella **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="6e13f-139">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e13f-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e13f-140">Example</span></span>  
 <span data-ttu-id="6e13f-141">Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il confronto binario come metodo predefinito per il confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="6e13f-141">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="6e13f-142">Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Binary` e inserirlo all'inizio del file di origine.</span><span class="sxs-lookup"><span data-stu-id="6e13f-142">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#45)]  
  
## <a name="example"></a><span data-ttu-id="6e13f-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e13f-143">Example</span></span>  
 <span data-ttu-id="6e13f-144">Nell'esempio seguente viene usata l'istruzione `Option Compare` per impostare il criterio di ordinamento del testo senza distinzione tra maiuscole e minuscole come metodo predefinito per il confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="6e13f-144">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="6e13f-145">Per usare questo codice, rimuovere il commento dall'istruzione `Option Compare Text` e inserirlo all'inizio del file di origine.</span><span class="sxs-lookup"><span data-stu-id="6e13f-145">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="6e13f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e13f-146">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>
- <xref:Microsoft.VisualBasic.Strings.Replace%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="6e13f-147">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="6e13f-147">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="6e13f-148">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="6e13f-148">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="6e13f-149">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e13f-149">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="6e13f-150">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="6e13f-150">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="6e13f-151">Funzioni stringa</span><span class="sxs-lookup"><span data-stu-id="6e13f-151">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)
- [<span data-ttu-id="6e13f-152">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="6e13f-152">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="6e13f-153">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="6e13f-153">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
