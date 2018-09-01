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
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Procedura: eseguire una query che restituisce tipi complessi
In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1.  Aggiungere il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [procedura: usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Fare doppio clic sul file edmx per visualizzare il modello nel [finestra Browser modello](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) di Entity Designer. Nell'area di Entity Designer, selezionare la `Email` e `Phone` delle proprietà delle `Contact` tipo di entità, quindi fare clic e scegliere **Effettua refactoring nel nuovo tipo complesso**.  
  
4.  Un nuovo tipo complesso all'elemento selezionato `Email` e `Phone` delle proprietà viene aggiunta per il **finestra Browser modello**. Il tipo complesso viene assegnato un nome predefinito: rinominare il tipo in `EmailPhone` nella **proprietà** finestra. Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`. Rinominare la proprietà in `EmailPhoneComplexType.`  
  
     Per informazioni sulla creazione e modifica di tipi complessi tramite la procedura guidata Entity Data Model, vedere [procedura: effettuare il refactoring di proprietà esistenti nella proprietà di un tipo complesso](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) e [procedura: creare e modificare tipi complessi](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` degli oggetti e vengono visualizzate due proprietà del `Contact` oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
