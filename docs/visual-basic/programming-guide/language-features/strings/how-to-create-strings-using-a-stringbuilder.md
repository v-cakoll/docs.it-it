---
title: 'Procedura: creare stringhe usando un oggetto StringBuilderHow to: create strings using a StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645332"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="23d72-102">Procedura: creare stringhe utilizzando un oggetto StringBuilder in Visual BasicHow to: create strings using a StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23d72-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="23d72-103">In questo esempio viene costruita una <xref:System.Text.StringBuilder> stringa lunga da molte stringhe più piccole utilizzando la classe .</span><span class="sxs-lookup"><span data-stu-id="23d72-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="23d72-104">La <xref:System.Text.StringBuilder> classe è più `&=` efficiente dell'operatore per la concatenazione di molte stringhe.</span><span class="sxs-lookup"><span data-stu-id="23d72-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="23d72-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="23d72-105">Example</span></span>

<span data-ttu-id="23d72-106">Nell'esempio seguente viene <xref:System.Text.StringBuilder> creata un'istanza della classe, vengono aggiunte 1.000 stringhe a tale istanza e quindi viene restituita la relativa rappresentazione di stringa:</span><span class="sxs-lookup"><span data-stu-id="23d72-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="23d72-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23d72-107">See also</span></span>

- [<span data-ttu-id="23d72-108">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="23d72-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="23d72-109">&- Operatore</span><span class="sxs-lookup"><span data-stu-id="23d72-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="23d72-110">Stringhe</span><span class="sxs-lookup"><span data-stu-id="23d72-110">Strings</span></span>](index.md)
- [<span data-ttu-id="23d72-111">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="23d72-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="23d72-112">Modifica di stringhe</span><span class="sxs-lookup"><span data-stu-id="23d72-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
