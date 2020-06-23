---
title: "Procedura: Creare un dominio dell'applicazione"
description: Vedere come creare un dominio applicazione in .NET. È possibile creare un dominio dell'applicazione per caricare gli assembly per gestirli personalmente o crearne uno per eseguire il codice.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 8e44e682f64854dbc0181b26f6ed3fa2905b7814
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104801"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="8273c-104">Procedura: Creare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8273c-104">How to: Create an Application Domain</span></span>
<span data-ttu-id="8273c-105">I domini dell'applicazione vengono creati automaticamente dall'host Common Language Runtime quando necessario.</span><span class="sxs-lookup"><span data-stu-id="8273c-105">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="8273c-106">È tuttavia possibile creare i propri domini dell'applicazione e caricarvi gli assembly che si vuole gestire personalmente.</span><span class="sxs-lookup"><span data-stu-id="8273c-106">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="8273c-107">È anche possibile creare domini dell'applicazione da cui eseguire codice.</span><span class="sxs-lookup"><span data-stu-id="8273c-107">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="8273c-108">Per creare un nuovo dominio dell'applicazione, usare uno dei metodi di overload **CreateDomain** nella classe <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8273c-108">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8273c-109">È possibile assegnare un nome al dominio dell'applicazione da usare per fare riferimento al dominio.</span><span class="sxs-lookup"><span data-stu-id="8273c-109">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="8273c-110">L'esempio seguente crea un nuovo dominio dell'applicazione, assegna al dominio il nome `MyDomain` e quindi stampa il nome del dominio host e del dominio dell'applicazione figlio appena creato nella console.</span><span class="sxs-lookup"><span data-stu-id="8273c-110">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8273c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8273c-111">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8273c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8273c-112">See also</span></span>

- [<span data-ttu-id="8273c-113">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8273c-113">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="8273c-114">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8273c-114">Using Application Domains</span></span>](use.md)
