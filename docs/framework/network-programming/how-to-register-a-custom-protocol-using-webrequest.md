---
title: 'Procedura: Registrare un protocollo personalizzato con WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1f78f98f94daa51c17a1294285e13dfddd457106
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47230969"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="a898d-102">Procedura: Registrare un protocollo personalizzato con WebRequest</span><span class="sxs-lookup"><span data-stu-id="a898d-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="a898d-103">Questo esempio mostra come registrare una classe specifica di un protocollo definita altrove.</span><span class="sxs-lookup"><span data-stu-id="a898d-103">This example shows how to register a protocol specific classthat is defined elsewhere.</span></span> <span data-ttu-id="a898d-104">In questo esempio, `CustomWebRequestCreator` è l'oggetto implementato dall'utente che implementa il metodo **Create** che restituisce l'oggetto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="a898d-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="a898d-105">Nell'esempio di codice si presuppone che sia stato scritto il codice `CustomWebRequest` che implementa il protocollo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a898d-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a898d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a898d-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a898d-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a898d-107">Compiling the Code</span></span>  
 <span data-ttu-id="a898d-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a898d-108">This example requires:</span></span>  
  
 <span data-ttu-id="a898d-109">Riferimenti allo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a898d-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a898d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a898d-110">See Also</span></span>  
 [<span data-ttu-id="a898d-111">Programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="a898d-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
