---
title: 'Procedura: creare stringhe utilizzando StringBuilder in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="f1260-102">Procedura: creare stringhe utilizzando StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1260-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="f1260-103">In questo esempio viene costruita una stringa lunga da molte stringhe più piccole utilizzando la <xref:System.Text.StringBuilder> classe.</span><span class="sxs-lookup"><span data-stu-id="f1260-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="f1260-104">Il <xref:System.Text.StringBuilder> classe risulta più efficiente il `&=` operatore per concatenare più stringhe.</span><span class="sxs-lookup"><span data-stu-id="f1260-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1260-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1260-105">Example</span></span>  
 <span data-ttu-id="f1260-106">Nell'esempio seguente crea un'istanza di <xref:System.Text.StringBuilder> classe aggiunte 1.000 stringhe a tale istanza e quindi restituisce la rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="f1260-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f1260-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1260-107">See Also</span></span>  
 [<span data-ttu-id="f1260-108">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="f1260-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="f1260-109">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="f1260-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="f1260-110">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f1260-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="f1260-111">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="f1260-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="f1260-112">Modifica di stringhe</span><span class="sxs-lookup"><span data-stu-id="f1260-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 [<span data-ttu-id="f1260-113">Esempio di stringhe</span><span class="sxs-lookup"><span data-stu-id="f1260-113">Strings Sample</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
