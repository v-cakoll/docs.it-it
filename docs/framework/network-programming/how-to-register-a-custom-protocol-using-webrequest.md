---
title: 'Procedura: Registrare un protocollo personalizzato con WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: d2056bee6c8847989556799511dfaea326dcdac1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669042"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="021f0-102">Procedura: Registrare un protocollo personalizzato con WebRequest</span><span class="sxs-lookup"><span data-stu-id="021f0-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="021f0-103">Questo esempio illustra come registrare una classe specifica di un protocollo definita altrove.</span><span class="sxs-lookup"><span data-stu-id="021f0-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="021f0-104">In questo esempio, `CustomWebRequestCreator` è l'oggetto implementato dall'utente che implementa il metodo **Create** che restituisce l'oggetto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="021f0-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="021f0-105">Nell'esempio di codice si presuppone che sia stato scritto il codice `CustomWebRequest` che implementa il protocollo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="021f0-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="021f0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="021f0-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="021f0-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="021f0-107">Compiling the Code</span></span>  
 <span data-ttu-id="021f0-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="021f0-108">This example requires:</span></span>  
  
 <span data-ttu-id="021f0-109">Riferimenti allo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="021f0-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021f0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="021f0-110">See also</span></span>
- [<span data-ttu-id="021f0-111">Programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="021f0-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
