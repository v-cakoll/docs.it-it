---
title: Aggiunta di logica di business mediante metodi parziali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 251d7a05971ff7940f85ec9d555d26f2e57067c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248128"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Aggiunta di logica di business mediante metodi parziali
È possibile personalizzare Visual Basic e C# il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] codice generato nei progetti usando *metodi parziali*. Il codice generato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce le firme come una parte di un metodo parziale. Se si desidera implementare il metodo, è possibile aggiungere un metodo parziale personalizzato. Se non si aggiunge un'implementazione personalizzata, il compilatore ignora la firma dei metodi parziali e chiama i metodi predefiniti in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
> Se si usa Visual Studio, è possibile usare la Object Relational Designer per aggiungere la convalida e altre personalizzazioni alle classi di entità.  
  
 Ad esempio, il mapping predefinito per la classe `Customer` nel database di esempio Northwind include il seguente metodo parziale:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 È possibile implementare un metodo personalizzato aggiungendo codice analogo al seguente alla classe parziale personalizzata `Customer`:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Questo approccio viene in genere usato [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in per eseguire l'override `Insert`dei metodi `Delete`predefiniti per, `Update`, e per convalidare le proprietà durante gli eventi del ciclo di vita dell'oggetto.  
  
 Per ulteriori informazioni, vedere [metodi parziali](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (MethodC# ) (Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio riportato di seguito viene illustrato innanzitutto come definire `ExampleClass` usando uno strumento per la generazione di codice quale SQLMetal, quindi come è possibile implementare solo uno dei due metodi.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>DESCRIZIONE  
 Nell'esempio riportato di seguito viene usata la relazione tra le entità `Shipper` e `Order`. Notare fra i metodi i metodi parziali `InsertShipper` e `DeleteShipper`. Questi metodi eseguono l'override dei metodi parziali [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] predefiniti forniti dal mapping.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
- [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md)
