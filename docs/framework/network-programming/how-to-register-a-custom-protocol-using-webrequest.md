---
title: 'Procedura: Registrare un protocollo personalizzato con WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 5f863aa61058e87a7911bab3b02c3ba345419596
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193604"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="5c796-102">Procedura: Registrare un protocollo personalizzato con WebRequest</span><span class="sxs-lookup"><span data-stu-id="5c796-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="5c796-103">Questo esempio mostra come registrare una classe specifica di un protocollo definita altrove.</span><span class="sxs-lookup"><span data-stu-id="5c796-103">This example shows how to register a protocol specific classthat is defined elsewhere.</span></span> <span data-ttu-id="5c796-104">In questo esempio, `CustomWebRequestCreator` è l'oggetto implementato dall'utente che implementa il metodo **Create** che restituisce l'oggetto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="5c796-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="5c796-105">Nell'esempio di codice si presuppone che sia stato scritto il codice `CustomWebRequest` che implementa il protocollo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5c796-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c796-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c796-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c796-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5c796-107">Compiling the Code</span></span>  
 <span data-ttu-id="5c796-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c796-108">This example requires:</span></span>  
  
 <span data-ttu-id="5c796-109">Riferimenti allo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="5c796-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c796-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c796-110">See Also</span></span>  
 [<span data-ttu-id="5c796-111">Programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="5c796-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
