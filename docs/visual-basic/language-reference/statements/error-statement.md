---
title: Istruzione Error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944448"
---
# <a name="error-statement"></a><span data-ttu-id="1697e-102">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="1697e-102">Error Statement</span></span>
<span data-ttu-id="1697e-103">Simula l'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="1697e-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1697e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1697e-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="1697e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1697e-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="1697e-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="1697e-106">Required.</span></span> <span data-ttu-id="1697e-107">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="1697e-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1697e-108">Note</span><span class="sxs-lookup"><span data-stu-id="1697e-108">Remarks</span></span>  
 <span data-ttu-id="1697e-109">L' `Error` istruzione è supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="1697e-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="1697e-110">Nel nuovo codice, in particolare quando si creano oggetti, `Err` utilizzare il `Raise` metodo dell'oggetto per generare errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="1697e-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="1697e-111">Se `errornumber` è definito, l' `Error` istruzione chiama il gestore degli errori `Err` dopo che alle proprietà dell'oggetto sono stati assegnati i valori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1697e-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="1697e-112">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1697e-112">Property</span></span>|<span data-ttu-id="1697e-113">Value</span><span class="sxs-lookup"><span data-stu-id="1697e-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="1697e-114">Valore specificato come argomento `Error` dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="1697e-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="1697e-115">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="1697e-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="1697e-116">Nome del progetto Visual Basic corrente.</span><span class="sxs-lookup"><span data-stu-id="1697e-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="1697e-117">Espressione stringa corrispondente al valore restituito della `Error` funzione per l'oggetto specificato `Number`, se questa stringa esiste.</span><span class="sxs-lookup"><span data-stu-id="1697e-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="1697e-118">Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").</span><span class="sxs-lookup"><span data-stu-id="1697e-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="1697e-119">L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.</span><span class="sxs-lookup"><span data-stu-id="1697e-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="1697e-120">ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente `Number` alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="1697e-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="1697e-121">Zero.</span><span class="sxs-lookup"><span data-stu-id="1697e-121">Zero.</span></span>|  
  
 <span data-ttu-id="1697e-122">Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato un messaggio di errore `Err` che viene visualizzato dalle proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1697e-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1697e-123">Alcune applicazioni host Visual Basic non possono creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="1697e-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="1697e-124">Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="1697e-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1697e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="1697e-125">Example</span></span>  
 <span data-ttu-id="1697e-126">In questo esempio viene `Error` utilizzata l'istruzione per generare il numero di errore 11.</span><span class="sxs-lookup"><span data-stu-id="1697e-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="1697e-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1697e-127">Requirements</span></span>  
 <span data-ttu-id="1697e-128">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="1697e-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="1697e-129">**Assembly** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="1697e-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1697e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1697e-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="1697e-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="1697e-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="1697e-132">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="1697e-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="1697e-133">Messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="1697e-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
