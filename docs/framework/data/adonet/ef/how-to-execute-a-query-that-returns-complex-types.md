---
title: 'Procedura: Eseguire una query che restituisce tipi complessi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b08b220e969ad1c400413978c85b2f107d64a688
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854647"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Procedura: Eseguire una query che restituisce tipi complessi
In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per l'utilizzo del Entity Framework. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Fare doppio clic sul file con estensione edmx per visualizzare il modello nella [finestra browser modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) della Entity Designer. Nell'area di `Email` Entity Designer selezionare le proprietà e `Phone` del tipo di `Contact` entità, quindi fare clic con il pulsante destro del mouse e selezionare **Effettua refactoring nel nuovo tipo complesso**.  
  
4. Un nuovo tipo complesso con le proprietà `Email` selezionate `Phone` e viene aggiunto a **browser modello**. Al tipo complesso viene assegnato un nome predefinito: rinominare il tipo `EmailPhone` in nella finestra **proprietà** . Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`. Rinominare la proprietà in `EmailPhoneComplexType.`  
  
     Per informazioni sulla creazione e la modifica di tipi complessi tramite la procedura guidata Entity Data Model [, vedere Procedura: Effettuare il refactoring delle proprietà esistenti in una](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) proprietà [di tipo complesso e procedura: Creare e modificare tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))complessi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` oggetti e vengono visualizzate due proprietà `Contact` degli oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
