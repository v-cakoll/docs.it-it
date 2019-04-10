---
title: 'Procedura: Eseguire una query che restituisce tipi complessi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: a428f54c3834ccdf6a0c7a5bfce8307172724524
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322888"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Procedura: Eseguire una query che restituisce tipi complessi
In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Fare doppio clic sul file edmx per visualizzare il modello nel [finestra Browser modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) di Entity Designer. Nell'area di Entity Designer, selezionare la `Email` e `Phone` delle proprietà delle `Contact` tipo di entità, quindi fare clic e scegliere **Effettua refactoring nel nuovo tipo complesso**.  
  
4. Un nuovo tipo complesso all'elemento selezionato `Email` e `Phone` delle proprietà viene aggiunta per il **finestra Browser modello**. Il tipo complesso viene assegnato un nome predefinito: rinominare il tipo in `EmailPhone` nella **proprietà** finestra. Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`. Rinominare la proprietà in `EmailPhoneComplexType.`  
  
     Per informazioni sulla creazione e modifica di tipi complessi tramite la procedura guidata Entity Data Model, vedere [come: Effettuare il refactoring di proprietà esistenti nella proprietà di un tipo complesso](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) e [come: Creare e modificare tipi complessi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` degli oggetti e vengono visualizzate due proprietà del `Contact` oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
