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
ms.openlocfilehash: 84fce92183228cbfa5554a3ba45770a86e83bff5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47232937"
---
# <a name="error-statement"></a><span data-ttu-id="9055f-102">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="9055f-102">Error Statement</span></span>
<span data-ttu-id="9055f-103">Simula il verificarsi di un errore.</span><span class="sxs-lookup"><span data-stu-id="9055f-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9055f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9055f-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="9055f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9055f-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="9055f-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9055f-106">Required.</span></span> <span data-ttu-id="9055f-107">Può essere qualsiasi numero errore valido.</span><span class="sxs-lookup"><span data-stu-id="9055f-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9055f-108">Note</span><span class="sxs-lookup"><span data-stu-id="9055f-108">Remarks</span></span>  
 <span data-ttu-id="9055f-109">Il `Error` istruzione è supportata per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9055f-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="9055f-110">Nel nuovo codice, soprattutto quando si creano oggetti, usare il `Err` dell'oggetto `Raise` metodo per generare errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="9055f-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="9055f-111">Se `errornumber` è definito, il `Error` istruzione chiama il gestore degli errori dopo le proprietà del `Err` oggetto vengono assegnati i valori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9055f-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="9055f-112">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9055f-112">Property</span></span>|<span data-ttu-id="9055f-113">Valore</span><span class="sxs-lookup"><span data-stu-id="9055f-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="9055f-114">Valore specificato come argomento per `Error` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9055f-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="9055f-115">Può essere qualsiasi numero errore valido.</span><span class="sxs-lookup"><span data-stu-id="9055f-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="9055f-116">Nome del progetto Visual Basic corrente.</span><span class="sxs-lookup"><span data-stu-id="9055f-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="9055f-117">Espressione corrispondente al valore restituito della stringa di `Error` funzione per l'oggetto specificato `Number`, se questa stringa è presente.</span><span class="sxs-lookup"><span data-stu-id="9055f-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="9055f-118">Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").</span><span class="sxs-lookup"><span data-stu-id="9055f-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="9055f-119">Il completo dell'unità, percorso e nome file del file della Guida di Visual Basic appropriato.</span><span class="sxs-lookup"><span data-stu-id="9055f-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="9055f-120">La Guida di Visual Basic di ID di contesto relativo all'errore corrispondente al file il `Number` proprietà.</span><span class="sxs-lookup"><span data-stu-id="9055f-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="9055f-121">Zero.</span><span class="sxs-lookup"><span data-stu-id="9055f-121">Zero.</span></span>|  
  
 <span data-ttu-id="9055f-122">Se nessun gestore di errori non esiste o non è attivato, un messaggio di errore verrà creato e visualizzato dal `Err` le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9055f-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9055f-123">Alcune applicazioni di host di Visual Basic non è possibile creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="9055f-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="9055f-124">Vedere la documentazione dell'applicazione host per determinare se può creare classi e oggetti.</span><span class="sxs-lookup"><span data-stu-id="9055f-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9055f-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="9055f-125">Example</span></span>  
 <span data-ttu-id="9055f-126">Questo esempio viene usato il `Error` istruzione per generare il numero di errore 11.</span><span class="sxs-lookup"><span data-stu-id="9055f-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="9055f-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9055f-127">Requirements</span></span>  
 <span data-ttu-id="9055f-128">**Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9055f-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9055f-129">**Assembly:** libreria di Runtime di Visual Basic (in VisualBasic)</span><span class="sxs-lookup"><span data-stu-id="9055f-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9055f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9055f-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [<span data-ttu-id="9055f-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="9055f-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [<span data-ttu-id="9055f-132">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="9055f-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="9055f-133">Messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="9055f-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
