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
ms.openlocfilehash: e819ba043dec2d5e8e792fdf57dc0c273a24e881
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654815"
---
# <a name="error-statement"></a><span data-ttu-id="c9daf-102">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="c9daf-102">Error Statement</span></span>
<span data-ttu-id="c9daf-103">Simula il verificarsi di un errore.</span><span class="sxs-lookup"><span data-stu-id="c9daf-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9daf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9daf-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="c9daf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c9daf-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="c9daf-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c9daf-106">Required.</span></span> <span data-ttu-id="c9daf-107">Può essere qualsiasi numero errore valido.</span><span class="sxs-lookup"><span data-stu-id="c9daf-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9daf-108">Note</span><span class="sxs-lookup"><span data-stu-id="c9daf-108">Remarks</span></span>  
 <span data-ttu-id="c9daf-109">Il `Error` istruzione è supportata per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c9daf-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="c9daf-110">Nel nuovo codice, soprattutto quando si creano oggetti, usare il `Err` dell'oggetto `Raise` metodo per generare errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="c9daf-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="c9daf-111">Se `errornumber` è definito, il `Error` istruzione chiama il gestore degli errori dopo le proprietà del `Err` oggetto vengono assegnati i valori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9daf-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="c9daf-112">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c9daf-112">Property</span></span>|<span data-ttu-id="c9daf-113">Value</span><span class="sxs-lookup"><span data-stu-id="c9daf-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="c9daf-114">Valore specificato come argomento per `Error` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c9daf-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="c9daf-115">Può essere qualsiasi numero errore valido.</span><span class="sxs-lookup"><span data-stu-id="c9daf-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="c9daf-116">Nome del progetto Visual Basic corrente.</span><span class="sxs-lookup"><span data-stu-id="c9daf-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="c9daf-117">Espressione corrispondente al valore restituito della stringa di `Error` funzione per l'oggetto specificato `Number`, se questa stringa è presente.</span><span class="sxs-lookup"><span data-stu-id="c9daf-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="c9daf-118">Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").</span><span class="sxs-lookup"><span data-stu-id="c9daf-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="c9daf-119">Il completo dell'unità, percorso e nome file del file della Guida di Visual Basic appropriato.</span><span class="sxs-lookup"><span data-stu-id="c9daf-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="c9daf-120">La Guida di Visual Basic di ID di contesto relativo all'errore corrispondente al file il `Number` proprietà.</span><span class="sxs-lookup"><span data-stu-id="c9daf-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="c9daf-121">Zero.</span><span class="sxs-lookup"><span data-stu-id="c9daf-121">Zero.</span></span>|  
  
 <span data-ttu-id="c9daf-122">Se nessun gestore di errori non esiste o non è attivato, un messaggio di errore verrà creato e visualizzato dal `Err` le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c9daf-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9daf-123">Alcune applicazioni di host di Visual Basic non è possibile creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="c9daf-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="c9daf-124">Vedere la documentazione dell'applicazione host per determinare se può creare classi e oggetti.</span><span class="sxs-lookup"><span data-stu-id="c9daf-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9daf-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9daf-125">Example</span></span>  
 <span data-ttu-id="c9daf-126">Questo esempio viene usato il `Error` istruzione per generare il numero di errore 11.</span><span class="sxs-lookup"><span data-stu-id="c9daf-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="c9daf-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9daf-127">Requirements</span></span>  
 <span data-ttu-id="c9daf-128">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="c9daf-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="c9daf-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="c9daf-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9daf-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9daf-130">See also</span></span>
- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="c9daf-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="c9daf-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="c9daf-132">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="c9daf-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="c9daf-133">Messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="c9daf-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
