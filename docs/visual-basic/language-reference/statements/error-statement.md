---
title: Istruzione Error
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
ms.openlocfilehash: 35ba1f19654d1d23ac1ec73564bc36b0af4f6777
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404745"
---
# <a name="error-statement"></a><span data-ttu-id="e2fca-102">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="e2fca-102">Error Statement</span></span>
<span data-ttu-id="e2fca-103">Simula l'occorrenza di un errore.</span><span class="sxs-lookup"><span data-stu-id="e2fca-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2fca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2fca-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="e2fca-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e2fca-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="e2fca-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2fca-106">Required.</span></span> <span data-ttu-id="e2fca-107">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="e2fca-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2fca-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="e2fca-108">Remarks</span></span>  
 <span data-ttu-id="e2fca-109">L' `Error` istruzione è supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e2fca-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="e2fca-110">Nel nuovo codice, in particolare quando si creano oggetti, utilizzare il `Err` metodo dell'oggetto `Raise` per generare errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="e2fca-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="e2fca-111">Se `errornumber` è definito, l' `Error` istruzione chiama il gestore degli errori dopo che alle proprietà dell' `Err` oggetto sono stati assegnati i valori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2fca-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="e2fca-112">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e2fca-112">Property</span></span>|<span data-ttu-id="e2fca-113">valore</span><span class="sxs-lookup"><span data-stu-id="e2fca-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="e2fca-114">Valore specificato come argomento dell' `Error` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e2fca-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="e2fca-115">Può essere qualsiasi numero di errore valido.</span><span class="sxs-lookup"><span data-stu-id="e2fca-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="e2fca-116">Nome del progetto Visual Basic corrente.</span><span class="sxs-lookup"><span data-stu-id="e2fca-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="e2fca-117">Espressione stringa corrispondente al valore restituito della `Error` funzione per l'oggetto specificato `Number` , se questa stringa esiste.</span><span class="sxs-lookup"><span data-stu-id="e2fca-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="e2fca-118">Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").</span><span class="sxs-lookup"><span data-stu-id="e2fca-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="e2fca-119">L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.</span><span class="sxs-lookup"><span data-stu-id="e2fca-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="e2fca-120">ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente alla `Number` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e2fca-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="e2fca-121">Zero.</span><span class="sxs-lookup"><span data-stu-id="e2fca-121">Zero.</span></span>|  
  
 <span data-ttu-id="e2fca-122">Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato un messaggio di errore che viene visualizzato dalle `Err` proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2fca-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2fca-123">Alcune applicazioni host Visual Basic non possono creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="e2fca-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="e2fca-124">Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="e2fca-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2fca-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2fca-125">Example</span></span>  
 <span data-ttu-id="e2fca-126">In questo esempio viene utilizzata l' `Error` istruzione per generare il numero di errore 11.</span><span class="sxs-lookup"><span data-stu-id="e2fca-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="e2fca-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2fca-127">Requirements</span></span>  
 <span data-ttu-id="e2fca-128">**Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="e2fca-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="e2fca-129">**Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="e2fca-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fca-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2fca-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="e2fca-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="e2fca-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="e2fca-132">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="e2fca-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="e2fca-133">messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="e2fca-133">Error Messages</span></span>](../error-messages/index.md)
