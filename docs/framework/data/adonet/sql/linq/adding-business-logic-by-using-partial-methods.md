---
title: Aggiunta di logica di business mediante metodi parziali
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
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9704ad7d4030ee85701f1f95f87c539c1fbd0122
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Aggiunta di logica di business mediante metodi parziali
È possibile personalizzare [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] e il codice in c# generato il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetti utilizzando *metodi parziali*. Il codice generato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce le firme come una parte di un metodo parziale. Se si desidera implementare il metodo, è possibile aggiungere un metodo parziale personalizzato. Se non si aggiunge un'implementazione personalizzata, il compilatore ignora la firma dei metodi parziali e chiama i metodi predefiniti in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
>  Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile usare la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per aggiungere la convalida e altre personalizzazioni alle classi di entità.  
  
 Ad esempio, il mapping predefinito per la classe `Customer` nel database di esempio Northwind include il seguente metodo parziale:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 È possibile implementare un metodo personalizzato aggiungendo codice analogo al seguente alla classe parziale personalizzata `Customer`:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Questo approccio viene utilizzato in genere [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override di metodi predefiniti per `Insert`, `Update`, `Delete`e per convalidare le proprietà durante gli eventi del ciclo di vita di oggetto.  
  
 Per ulteriori informazioni, vedere [metodi parziali](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) o [parziale (metodo) (riferimenti per c#)](~/docs/csharp/language-reference/keywords/partial-method.md) (c#).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio riportato di seguito viene illustrato innanzitutto come definire `ExampleClass` usando uno strumento per la generazione di codice quale SQLMetal, quindi come è possibile implementare solo uno dei due metodi.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio riportato di seguito viene usata la relazione tra le entità `Shipper` e `Order`. Notare fra i metodi i metodi parziali `InsertShipper` e `DeleteShipper`. Questi metodi eseguono l'override dei metodi parziali predefiniti forniti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
