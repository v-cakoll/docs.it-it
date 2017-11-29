---
title: 'Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4a682c7ae32ace0b1f859d52963342546a83f29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="57932-102">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57932-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="57932-103">Si dichiara una variabile del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) specificando `As Object` in un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="57932-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="57932-104">Assegnare un oggetto a tale variabile inserendo l'oggetto dopo il segno di uguale (`=`) in una clausola di istruzione o l'inizializzazione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="57932-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57932-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="57932-105">Example</span></span>  
 <span data-ttu-id="57932-106">Nell'esempio seguente viene dichiarato un `Object` variabile e assegna l'istanza corrente a esso.</span><span class="sxs-lookup"><span data-stu-id="57932-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="57932-107">È possibile combinare la dichiarazione e l'assegnazione inizializzando la variabile come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="57932-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="57932-108">Nell'esempio seguente è equivalente all'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="57932-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57932-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="57932-109">Compiling the Code</span></span>  
 <span data-ttu-id="57932-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="57932-110">This example requires:</span></span>  
  
-   <span data-ttu-id="57932-111">Un riferimento allo spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="57932-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="57932-112">Una classe, struttura o modulo in cui inserire il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57932-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="57932-113">Una procedura in cui inserire l'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="57932-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57932-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57932-114">See Also</span></span>  
 [<span data-ttu-id="57932-115">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="57932-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="57932-116">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="57932-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="57932-117">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="57932-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="57932-118">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="57932-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="57932-119">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="57932-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="57932-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="57932-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="57932-121">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="57932-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
