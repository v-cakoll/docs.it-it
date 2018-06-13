---
title: 'Procedura: inserire righe nel database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 4f46e38642d42e3a2e4d5f05e23cc76cf431119b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361734"
---
# <a name="how-to-insert-rows-into-the-database"></a>Procedura: inserire righe nel database
Per inserire righe in un database tramite l'aggiunta di oggetti associati [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> raccolta, quindi inviando le modifiche al database. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traduce le modifiche in SQL appropriate `INSERT` comandi.  
  
> [!NOTE]
>  È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure allo stesso scopo.  
  
 Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind. Per ulteriori informazioni, vedere [procedura: connettersi a un Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-insert-a-row-into-the-database"></a>Per inserire una riga nel database  
  
1.  Creare un nuovo oggetto contenente i dati della colonna da inviare.  
  
2.  Aggiungere il nuovo oggetto per il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` raccolta associata alla tabella di destinazione nel database.  
  
3.  Inviare le modifiche al database.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente consente di creare un nuovo oggetto di tipo `Order` e di popolarlo con i valori corretti. Il nuovo oggetto viene quindi aggiunto alla raccolta `Order`. Infine viene inviata la modifica al database come una nuova riga nella tabella `Orders`.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
