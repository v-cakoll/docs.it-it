---
title: "Procedura: Creare un dominio dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 83bf0ad96b352ed5c015723dd89aee7913d2a88e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119879"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="80967-102">Procedura: Creare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="80967-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="80967-103">I domini dell'applicazione vengono creati automaticamente dall'host Common Language Runtime quando necessario.</span><span class="sxs-lookup"><span data-stu-id="80967-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="80967-104">È tuttavia possibile creare i propri domini dell'applicazione e caricarvi gli assembly che si vuole gestire personalmente.</span><span class="sxs-lookup"><span data-stu-id="80967-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="80967-105">È anche possibile creare domini dell'applicazione da cui eseguire codice.</span><span class="sxs-lookup"><span data-stu-id="80967-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="80967-106">Per creare un nuovo dominio dell'applicazione, usare uno dei metodi di overload **CreateDomain** nella classe <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80967-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="80967-107">È possibile assegnare un nome al dominio dell'applicazione da usare per fare riferimento al dominio.</span><span class="sxs-lookup"><span data-stu-id="80967-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="80967-108">L'esempio seguente crea un nuovo dominio dell'applicazione, assegna al dominio il nome `MyDomain` e quindi stampa il nome del dominio host e del dominio dell'applicazione figlio appena creato nella console.</span><span class="sxs-lookup"><span data-stu-id="80967-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80967-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="80967-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="80967-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80967-110">See also</span></span>

- [<span data-ttu-id="80967-111">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="80967-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="80967-112">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="80967-112">Using Application Domains</span></span>](use.md)
