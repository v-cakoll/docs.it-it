---
title: 'Procedura: eseguire una query che restituisce tipi complessi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9bdd2ba859e97be12cfc4049c73c33ce1402e355
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Procedura: eseguire una query che restituisce tipi complessi
In questo argomento viene illustrato come eseguire una query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che restituisce oggetti del tipo di entità contenenti una proprietà di un tipo complesso.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1.  Aggiungere il [modello Sales di AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto utilizzerà il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Fare doppio clic sul file edmx per visualizzare il modello nella [finestra Browser modello](http://msdn.microsoft.com/en-us/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) di Entity Designer. Nell'area di Entity Designer, selezionare il `Email` e `Phone` le proprietà del `Contact` tipo di entità, quindi fare clic e scegliere **effettuare il refactoring in nuovo tipo complesso**.  
  
4.  Un nuovo tipo complesso con l'elemento `Email` e `Phone` proprietà viene aggiunta per il **Browser modello**. Il tipo complesso viene assegnato un nome predefinito: rinominare il tipo in `EmailPhone` nel **proprietà** finestra. Viene inoltre aggiunta, una nuova proprietà `ComplexProperty` al tipo di entità `Contact`. Rinominare la proprietà in `EmailPhoneComplexType.`  
  
     Per informazioni sulla creazione e modifica dei tipi complessi mediante la procedura guidata Entity Data Model, vedere [procedura: effettuare il refactoring di proprietà esistenti in una proprietà di tipo complesso](http://msdn.microsoft.com/en-us/5b2eb3b3-693d-42cb-b43a-405812d677eb) e [procedura: creare e modificare i tipi complessi](http://msdn.microsoft.com/en-us/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query che restituisce una raccolta di `Contact` oggetti e visualizza due proprietà del `Contact` oggetti: `ContactID` e i valori del `EmailPhoneComplexType` tipo complesso.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
