---
title: Utilizzo di gestori eccezioni filtrati dall'utente
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: 5537404178b746310f720c5b0c075c77287dda4c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708453"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="91c18-102">Utilizzo di gestori eccezioni filtrati dall'utente</span><span class="sxs-lookup"><span data-stu-id="91c18-102">Using User-Filtered Exception Handlers</span></span>

<span data-ttu-id="91c18-103">In Visual Basic sono attualmente supportate eccezioni filtrate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91c18-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="91c18-104">I gestori di eccezioni filtrati dall'utente intercettano e gestiscono le eccezioni in base a requisiti definiti dall'utente per le singole eccezioni.</span><span class="sxs-lookup"><span data-stu-id="91c18-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="91c18-105">Tali gestori usano l'istruzione **Catch** con la parola chiave **When**.</span><span class="sxs-lookup"><span data-stu-id="91c18-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="91c18-106">Questa tecnica è utile quando un particolare oggetto eccezione corrisponde a più errori.</span><span class="sxs-lookup"><span data-stu-id="91c18-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="91c18-107">In questo caso l'oggetto presenta in genere una proprietà che contiene il codice di errore specifico associato all'errore.</span><span class="sxs-lookup"><span data-stu-id="91c18-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="91c18-108">È possibile usare la proprietà del codice di errore nell'espressione per selezionare solo l'errore particolare che si desidera gestire in tale clausola **Catch**.</span><span class="sxs-lookup"><span data-stu-id="91c18-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="91c18-109">L'esempio di Visual Basic seguente illustra l'istruzione **Catch/When**.</span><span class="sxs-lookup"><span data-stu-id="91c18-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="91c18-110">L'espressione della clausola filtrata dall'utente non è sottoposta ad alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="91c18-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="91c18-111">Se durante l'esecuzione dell'espressione filtrata dall'utente si verifica un'eccezione, quest'ultima viene ignorata e si considera che l'espressione di filtro abbia restituito il valore false.</span><span class="sxs-lookup"><span data-stu-id="91c18-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="91c18-112">In questo caso Common Language Runtime continua la ricerca di un gestore per l'eccezione corrente.</span><span class="sxs-lookup"><span data-stu-id="91c18-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="91c18-113">Combinazione di un'eccezione specifica e di clausole filtrate dall'utente</span><span class="sxs-lookup"><span data-stu-id="91c18-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="91c18-114">Un'istruzione catch può contenere sia l'eccezione specifica che le clausole filtrate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91c18-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="91c18-115">Nel runtime viene prima eseguito il test dell'eccezione specifica.</span><span class="sxs-lookup"><span data-stu-id="91c18-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="91c18-116">Se l'eccezione specifica ha esito positivo, verrà eseguito il filtro dell'utente.</span><span class="sxs-lookup"><span data-stu-id="91c18-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="91c18-117">Il filtro generico può contenere un riferimento alla variabile dichiarata nel filtro della classe.</span><span class="sxs-lookup"><span data-stu-id="91c18-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="91c18-118">Si noti che non è possibile invertire l'ordine delle due clausole di filtro.</span><span class="sxs-lookup"><span data-stu-id="91c18-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="91c18-119">L'esempio di Visual Basic seguente illustra l'eccezione specifica `ClassLoadException` nell'istruzione **Catch** e la clausola filtrata dall'utente che usa la parola chiave **When**.</span><span class="sxs-lookup"><span data-stu-id="91c18-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="91c18-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c18-120">See also</span></span>

- [<span data-ttu-id="91c18-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="91c18-121">Exceptions</span></span>](index.md)
