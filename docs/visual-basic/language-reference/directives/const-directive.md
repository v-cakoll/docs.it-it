---
title: '#Direttiva Const'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415466"
---
# <a name="const-directive"></a><span data-ttu-id="dfdbd-102">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="dfdbd-102">#Const Directive</span></span>

<span data-ttu-id="dfdbd-103">Definisce le costanti del compilatore condizionale per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfdbd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfdbd-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="dfdbd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="dfdbd-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="dfdbd-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-106">Required.</span></span> <span data-ttu-id="dfdbd-107">Nome della costante da definire.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="dfdbd-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-108">Required.</span></span> <span data-ttu-id="dfdbd-109">Valore letterale, altra costante del compilatore condizionale o qualsiasi combinazione che includa tutti gli operatori aritmetici o logici eccetto `Is` .</span><span class="sxs-lookup"><span data-stu-id="dfdbd-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfdbd-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="dfdbd-110">Remarks</span></span>  

 <span data-ttu-id="dfdbd-111">Le costanti del compilatore condizionale sono sempre private per il file in cui sono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="dfdbd-112">Non è possibile creare costanti del compilatore pubbliche usando la `#Const` direttiva. è possibile crearle solo nell'interfaccia utente o con l' `/define` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="dfdbd-113">È possibile utilizzare solo le costanti del compilatore condizionale e i valori letterali in `expression` .</span><span class="sxs-lookup"><span data-stu-id="dfdbd-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="dfdbd-114">L'uso di una costante standard definita con `Const` causa un errore.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="dfdbd-115">Viceversa, è possibile utilizzare le costanti definite con la `#Const` parola chiave solo per la compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="dfdbd-116">Le costanti possono anche essere indefinite, nel qual caso hanno un valore di `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="dfdbd-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfdbd-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfdbd-117">Example</span></span>  

 <span data-ttu-id="dfdbd-118">In questo esempio viene usata la direttiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="dfdbd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfdbd-119">See also</span></span>

- [<span data-ttu-id="dfdbd-120">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfdbd-120">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
- [<span data-ttu-id="dfdbd-121">#If... Direttive then... #Else</span><span class="sxs-lookup"><span data-stu-id="dfdbd-121">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="dfdbd-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="dfdbd-122">Const Statement</span></span>](../statements/const-statement.md)
- [<span data-ttu-id="dfdbd-123">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="dfdbd-123">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="dfdbd-124">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="dfdbd-124">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
