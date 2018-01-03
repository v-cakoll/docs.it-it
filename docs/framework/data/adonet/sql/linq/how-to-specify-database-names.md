---
title: 'Procedura: specificare nomi di database'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d0dffe22205b2d59dbd77bcd8f86efe4fa56be3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="849d4-102">Procedura: specificare nomi di database</span><span class="sxs-lookup"><span data-stu-id="849d4-102">How to: Specify Database Names</span></span>
<span data-ttu-id="849d4-103">Usare la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> su un attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> per specificare il nome di un database quando non viene fornito dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="849d4-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="849d4-104">Per alcuni esempi di codice, vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="849d4-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="849d4-105">Per specificare il nome del database</span><span class="sxs-lookup"><span data-stu-id="849d4-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="849d4-106">Aggiungere l'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> alla dichiarazione di classe per il database.</span><span class="sxs-lookup"><span data-stu-id="849d4-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="849d4-107">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> all'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="849d4-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="849d4-108">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> sul nome che si desidera specificare.</span><span class="sxs-lookup"><span data-stu-id="849d4-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849d4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="849d4-109">See Also</span></span>  
 [<span data-ttu-id="849d4-110">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="849d4-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="849d4-111">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="849d4-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
