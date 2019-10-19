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
ms.openlocfilehash: c7b2adfe7f6b6ff5e89598cb318a90c51595ff6f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583371"
---
# <a name="error-statement"></a><span data-ttu-id="258a6-102">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="258a6-102">Error Statement</span></span>
<span data-ttu-id="258a6-103">Simula l'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="258a6-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="258a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="258a6-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="258a6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="258a6-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="258a6-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="258a6-106">Required.</span></span> <span data-ttu-id="258a6-107">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="258a6-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="258a6-108">Note</span><span class="sxs-lookup"><span data-stu-id="258a6-108">Remarks</span></span>  
 <span data-ttu-id="258a6-109">L'istruzione `Error` è supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="258a6-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="258a6-110">Nel nuovo codice, in particolare quando si creano oggetti, utilizzare il metodo `Raise` dell'oggetto `Err` per generare errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="258a6-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="258a6-111">Se `errornumber` è stato definito, l'istruzione `Error` chiama il gestore degli errori dopo che alle proprietà dell'oggetto `Err` vengono assegnati i valori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="258a6-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="258a6-112">proprietà</span><span class="sxs-lookup"><span data-stu-id="258a6-112">Property</span></span>|<span data-ttu-id="258a6-113">Value</span><span class="sxs-lookup"><span data-stu-id="258a6-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="258a6-114">Valore specificato come argomento per `Error` istruzione.</span><span class="sxs-lookup"><span data-stu-id="258a6-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="258a6-115">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="258a6-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="258a6-116">Nome del progetto Visual Basic corrente.</span><span class="sxs-lookup"><span data-stu-id="258a6-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="258a6-117">Espressione stringa corrispondente al valore restituito della funzione `Error` per la `Number` specificata, se questa stringa esiste.</span><span class="sxs-lookup"><span data-stu-id="258a6-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="258a6-118">Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").</span><span class="sxs-lookup"><span data-stu-id="258a6-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="258a6-119">L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.</span><span class="sxs-lookup"><span data-stu-id="258a6-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="258a6-120">ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente alla proprietà `Number`.</span><span class="sxs-lookup"><span data-stu-id="258a6-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="258a6-121">Zero.</span><span class="sxs-lookup"><span data-stu-id="258a6-121">Zero.</span></span>|  
  
 <span data-ttu-id="258a6-122">Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato e visualizzato un messaggio di errore dalle proprietà dell'oggetto `Err`.</span><span class="sxs-lookup"><span data-stu-id="258a6-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="258a6-123">Alcune applicazioni host Visual Basic non possono creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="258a6-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="258a6-124">Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="258a6-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="258a6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="258a6-125">Example</span></span>  
 <span data-ttu-id="258a6-126">In questo esempio viene utilizzata l'istruzione `Error` per generare il numero di errore 11.</span><span class="sxs-lookup"><span data-stu-id="258a6-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="258a6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="258a6-127">Requirements</span></span>  
 <span data-ttu-id="258a6-128">**Spazio dei nomi:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="258a6-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="258a6-129">**Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="258a6-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="258a6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="258a6-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="258a6-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="258a6-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="258a6-132">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="258a6-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="258a6-133">Messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="258a6-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
