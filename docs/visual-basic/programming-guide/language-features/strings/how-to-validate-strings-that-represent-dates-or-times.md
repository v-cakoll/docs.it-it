---
title: 'Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685399"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="a9f78-102">Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9f78-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="a9f78-103">I seguente esempio di codice impostare un `Boolean` valore che indica se una stringa rappresenta una data valida o un'ora.</span><span class="sxs-lookup"><span data-stu-id="a9f78-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f78-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9f78-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9f78-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a9f78-105">Compiling the Code</span></span>  
 <span data-ttu-id="a9f78-106">Sostituire `("01/01/03")` e `"9:30 PM"` con la data e ora che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="a9f78-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="a9f78-107">È possibile sostituire la stringa con un'altra stringa hardcoded, con un `String` variabile, o con un metodo che restituisce una stringa, ad esempio `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="a9f78-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a9f78-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="a9f78-108">Robust Programming</span></span>  
 <span data-ttu-id="a9f78-109">Usare questo metodo per convalidare la stringa prima di tentare di convertire le `String` a un `DateTime` variabile.</span><span class="sxs-lookup"><span data-stu-id="a9f78-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="a9f78-110">Controllando la data o ora prima di tutto, è possibile evitare la generazione di un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a9f78-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f78-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9f78-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="a9f78-112">Convalida delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9f78-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
