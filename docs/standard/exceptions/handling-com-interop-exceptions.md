---
title: Gestione di eccezioni per interoperabilità COM
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
ms.openlocfilehash: 17cd739ac40b43bdd4a93b83a4ab9d0d92400e2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708932"
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="555c8-102">Gestione di eccezioni per interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="555c8-102">Handling COM Interop Exceptions</span></span>
<span data-ttu-id="555c8-103">Il codice gestito può essere integrato con il codice non gestito per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="555c8-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="555c8-104">Se un metodo genera un'eccezione nel codice gestito, Common Language Runtime può passare un valore HRESULT a un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="555c8-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="555c8-105">Se un metodo non riesce nel codice non gestito, restituendo un HRESULT di errore, il runtime genera un'eccezione che può essere intercettata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="555c8-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="555c8-106">Il runtime esegue automaticamente il mapping HRESULT dall'interoperabilità COM per le eccezioni più specifiche.</span><span class="sxs-lookup"><span data-stu-id="555c8-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="555c8-107">Ad esempio, E_ACCESSDENIED diventa <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY diventa <xref:System.OutOfMemoryException>, e così via.</span><span class="sxs-lookup"><span data-stu-id="555c8-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="555c8-108">Se il valore HRESULT è un risultato personalizzato o se è noto al runtime, il runtime passa un oggetto generico <xref:System.Runtime.InteropServices.COMException> al client.</span><span class="sxs-lookup"><span data-stu-id="555c8-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="555c8-109">La proprietà **ErrorCode** di **COMException** contiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="555c8-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="555c8-110">Uso di IErrorInfo</span><span class="sxs-lookup"><span data-stu-id="555c8-110">Working with IErrorInfo</span></span>  
 <span data-ttu-id="555c8-111">Quando un errore viene passato da COM al codice gestito, il runtime compila l'oggetto eccezione con informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="555c8-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="555c8-112">Gli oggetti COM che supportano IErrorInfo e restituiscono valori HRESULT forniscono queste informazioni per le eccezioni del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="555c8-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="555c8-113">Ad esempio, il runtime esegue il mapping della descrizione dell'errore COM alla proprietà <xref:System.Exception.Message%2A> dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="555c8-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="555c8-114">Se il valore HRESULT non fornisce alcuna informazione di errore, il runtime compila molte delle proprietà dell'eccezione con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="555c8-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="555c8-115">Se un metodo non riesce nel codice non gestito, un'eccezione può essere passata a un segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="555c8-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="555c8-116">L'argomento [HRESULT ed eccezioni](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contiene una tabella che mostra il mapping di HRESULT a oggetti eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="555c8-116">The topic [HRESULTS and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="555c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="555c8-117">See also</span></span>

- [<span data-ttu-id="555c8-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="555c8-118">Exceptions</span></span>](index.md)
