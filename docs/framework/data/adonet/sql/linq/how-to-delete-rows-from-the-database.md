---
title: 'Procedura: Eliminare righe dal database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 421735567c527ac9a70cc5eefdbd7570599faac7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782011"
---
# <a name="how-to-delete-rows-from-the-database"></a>Procedura: Eliminare righe dal database

È possibile eliminare righe in un database rimuovendo gli oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] corrispondenti dalla raccolta relativa alla tabella. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]converte le modifiche apportate ai comandi SQL `DELETE` appropriati.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta o non riconosce operazioni di eliminazione a catena. Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario effettuare una delle attività seguenti:

- Impostare la regola `ON DELETE CASCADE` nel vincolo di chiave esterna del database.

- Usare il codice personalizzato per eliminare prima gli oggetti figlio che impediscono l'eliminazione dell'oggetto padre.

 In caso contrario, viene generata un'eccezione. Vedere il secondo esempio di codice riportato più avanti in questo argomento.

> [!NOTE]
> È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).
>
> Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.

Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind. Per altre informazioni, vedere [Procedura: Connettersi a un database](how-to-connect-to-a-database.md).

### <a name="to-delete-a-row-in-the-database"></a>Per eliminare una riga dal database

1. Eseguire una query sul database per la riga da eliminare.

2. Chiamare il metodo <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.

3. Inviare le modifiche al database.

## <a name="example"></a>Esempio

Nel primo esempio di codice viene eseguita una query sul database per ottenere dettagli relativi all'ordine N. 11000, questi dettagli relativi all'ordine vengono contrassegnati per l'eliminazione e tali modifiche vengono inviate al database.

[!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
[!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]

## <a name="example"></a>Esempio

Nel secondo esempio, l'obiettivo è l'eliminazione di un ordine (N. 10250). Il codice esamina innanzitutto la tabella `OrderDetails` per verificare se l'ordine da eliminare dispone di elementi figlio. In tal caso, gli elementi figlio e successivamente l'ordine vengono contrassegnati per l'eliminazione. L'oggetto <xref:System.Data.Linq.DataContext> ordina correttamente le eliminazioni effettive in modo che i comandi di eliminazione inviati al database si attengano ai vincoli del database.

[!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
[!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
