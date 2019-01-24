---
title: 'Procedura: Compilare una stringa di connessione EntityConnection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: a78d325b5a687a09ef1d1e627c5894808538aaa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632760"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="e0ec3-102">Procedura: Compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="e0ec3-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="e0ec3-103">In questo argomento viene fornito un esempio di come compilare un oggetto <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="e0ec3-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="e0ec3-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="e0ec3-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="e0ec3-105">Aggiungere il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0ec3-105">Add the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="e0ec3-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="e0ec3-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="e0ec3-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="e0ec3-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="e0ec3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0ec3-108">Example</span></span>  
 <span data-ttu-id="e0ec3-109">Nell'esempio seguente viene inizializzato l'oggetto <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> per il provider sottostante, quindi viene inizializzato l'oggetto <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>, che viene passato al costruttore di <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="e0ec3-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="e0ec3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0ec3-110">See also</span></span>
- [<span data-ttu-id="e0ec3-111">Procedura: Utilizzare EntityConnection con un contesto dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="e0ec3-111">How to: Use EntityConnection with an Object Context</span></span>](https://msdn.microsoft.com/library/2140fe7b-b88b-47c8-a749-d7f142eb1080)
- [<span data-ttu-id="e0ec3-112">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="e0ec3-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
