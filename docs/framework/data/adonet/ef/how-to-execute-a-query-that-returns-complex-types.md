---
title: 'Procedura: Eseguire una Query che restituisce tipi complessi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 6c063c9ef6bfde868c773d941ba2107dbaa9ee73
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827123"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="d5261-102">Procedura: Eseguire una Query che restituisce tipi complessi</span><span class="sxs-lookup"><span data-stu-id="d5261-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="d5261-103">In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="d5261-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="d5261-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="d5261-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="d5261-105">Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5261-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="d5261-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d5261-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="d5261-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="d5261-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="d5261-108">Fare doppio clic sul file edmx per visualizzare il modello nel [finestra Browser modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) di Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="d5261-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="d5261-109">Nell'area di Entity Designer, selezionare la `Email` e `Phone` delle proprietà delle `Contact` tipo di entità, quindi fare clic e scegliere **Effettua refactoring nel nuovo tipo complesso**.</span><span class="sxs-lookup"><span data-stu-id="d5261-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="d5261-110">Un nuovo tipo complesso all'elemento selezionato `Email` e `Phone` delle proprietà viene aggiunta per il **finestra Browser modello**.</span><span class="sxs-lookup"><span data-stu-id="d5261-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="d5261-111">Il tipo complesso viene assegnato un nome predefinito: rinominare il tipo in `EmailPhone` nella **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d5261-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="d5261-112">Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`.</span><span class="sxs-lookup"><span data-stu-id="d5261-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="d5261-113">Rinominare la proprietà in `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="d5261-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="d5261-114">Per informazioni sulla creazione e modifica di tipi complessi tramite la procedura guidata Entity Data Model, vedere [come: Effettuare il refactoring di proprietà esistenti nella proprietà di un tipo complesso](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) e [come: Creare e modificare tipi complessi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d5261-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5261-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5261-115">Example</span></span>  
 <span data-ttu-id="d5261-116">Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` degli oggetti e vengono visualizzate due proprietà del `Contact` oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="d5261-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
