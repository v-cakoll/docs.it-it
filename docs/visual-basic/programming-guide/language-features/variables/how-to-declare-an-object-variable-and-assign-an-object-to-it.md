---
title: 'Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: e172d62e5bfadded254d5a5fd25b1dcf2da9634d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663586"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="57824-102">Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57824-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="57824-103">Si dichiara una variabile del [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) specificando `As Object` in un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="57824-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="57824-104">Si assegna un oggetto a tale variabile posizionando l'oggetto dopo il segno di uguale (`=`) in una clausola di istruzione o l'inizializzazione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="57824-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57824-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="57824-105">Example</span></span>  
 <span data-ttu-id="57824-106">Nell'esempio seguente viene dichiarato un `Object` variabile e assegna a esso dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="57824-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="57824-107">È possibile combinare la dichiarazione e l'assegnazione inizializzando la variabile come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="57824-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="57824-108">Nell'esempio seguente è equivalente all'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="57824-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57824-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="57824-109">Compiling the Code</span></span>  
 <span data-ttu-id="57824-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="57824-110">This example requires:</span></span>  
  
- <span data-ttu-id="57824-111">Un riferimento allo spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="57824-111">A reference to the <xref:System> namespace.</span></span>  
  
- <span data-ttu-id="57824-112">Una classe, struttura o modulo in cui inserire il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57824-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
- <span data-ttu-id="57824-113">Una procedura in cui inserire l'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="57824-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57824-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57824-114">See also</span></span>

- [<span data-ttu-id="57824-115">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="57824-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="57824-116">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="57824-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="57824-117">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="57824-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="57824-118">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="57824-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="57824-119">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="57824-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="57824-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="57824-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="57824-121">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="57824-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
