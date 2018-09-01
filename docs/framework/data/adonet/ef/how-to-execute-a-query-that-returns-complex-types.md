---
title: 'Procedura: eseguire una query che restituisce tipi complessi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 013f1980d2ea13927871719aeea293cfce38b4d5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385307"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="5949f-102">Procedura: eseguire una query che restituisce tipi complessi</span><span class="sxs-lookup"><span data-stu-id="5949f-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="5949f-103">In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="5949f-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="5949f-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="5949f-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="5949f-105">Aggiungere il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5949f-105">Add the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="5949f-106">Per altre informazioni, vedere [procedura: usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="5949f-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="5949f-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="5949f-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="5949f-108">Fare doppio clic sul file edmx per visualizzare il modello nel [finestra Browser modello](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) di Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="5949f-108">Double click the .edmx file to display the model in the [Model Browser window](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) of the Entity Designer.</span></span> <span data-ttu-id="5949f-109">Nell'area di Entity Designer, selezionare la `Email` e `Phone` delle proprietà delle `Contact` tipo di entità, quindi fare clic e scegliere **Effettua refactoring nel nuovo tipo complesso**.</span><span class="sxs-lookup"><span data-stu-id="5949f-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4.  <span data-ttu-id="5949f-110">Un nuovo tipo complesso all'elemento selezionato `Email` e `Phone` delle proprietà viene aggiunta per il **finestra Browser modello**.</span><span class="sxs-lookup"><span data-stu-id="5949f-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="5949f-111">Il tipo complesso viene assegnato un nome predefinito: rinominare il tipo in `EmailPhone` nella **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="5949f-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="5949f-112">Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`.</span><span class="sxs-lookup"><span data-stu-id="5949f-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="5949f-113">Rinominare la proprietà in `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="5949f-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="5949f-114">Per informazioni sulla creazione e modifica di tipi complessi tramite la procedura guidata Entity Data Model, vedere [procedura: effettuare il refactoring di proprietà esistenti nella proprietà di un tipo complesso](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) e [procedura: creare e modificare tipi complessi](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span><span class="sxs-lookup"><span data-stu-id="5949f-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) and [How to: Create and Modify Complex Types](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5949f-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="5949f-115">Example</span></span>  
 <span data-ttu-id="5949f-116">Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` degli oggetti e vengono visualizzate due proprietà del `Contact` oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="5949f-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
