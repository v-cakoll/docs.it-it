---
title: 'Procedura: visualizzare il codice SQL generato'
description: Informazioni su come visualizzare il codice SQL generato per le query usando la proprietà log per comprendere LINQ to SQL funzionalità e per il debug.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 5e75a8aadf4631f0a6e50641db72ba7b83af41fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286378"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="60e1b-103">Procedura: visualizzare il codice SQL generato</span><span class="sxs-lookup"><span data-stu-id="60e1b-103">How to: Display Generated SQL</span></span>
<span data-ttu-id="60e1b-104">È possibile visualizzare il codice SQL generato per le query e modificare l'elaborazione usando la proprietà <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e1b-104">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="60e1b-105">Questo approccio può essere utile per comprendere la funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e per eseguire il debug di problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="60e1b-105">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e1b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="60e1b-106">Example</span></span>  
 <span data-ttu-id="60e1b-107">Nell'esempio riportato di seguito viene usata la proprietà <xref:System.Data.Linq.DataContext.Log%2A> per visualizzare il codice SQL nella finestra della console prima di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="60e1b-107">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="60e1b-108">È possibile usare questa proprietà con comandi di query, inserimento, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="60e1b-108">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="60e1b-109">Le linee dalla finestra della console sono quelle visualizzate quando si esegue il codice Visual Basic o C# seguente.</span><span class="sxs-lookup"><span data-stu-id="60e1b-109">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="60e1b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60e1b-110">See also</span></span>

- [<span data-ttu-id="60e1b-111">Supporto per il debug</span><span class="sxs-lookup"><span data-stu-id="60e1b-111">Debugging Support</span></span>](debugging-support.md)
