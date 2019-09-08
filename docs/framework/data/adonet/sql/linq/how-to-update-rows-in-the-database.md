---
title: 'Procedura: Aggiornare righe nel database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: c2055e1dd988352b50a439531ab5533f34a4965e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793127"
---
# <a name="how-to-update-rows-in-the-database"></a>Procedura: Aggiornare righe nel database

È possibile aggiornare le righe in un database modificando i valori dei membri degli oggetti associati [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> alla raccolta e quindi inviando le modifiche al database. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]converte le modifiche nei comandi SQL `UPDATE` appropriati.

> [!NOTE]
> È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).
>
> Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.

Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind. Per altre informazioni, vedere [Procedura: Connettersi a un database](how-to-connect-to-a-database.md).

### <a name="to-update-a-row-in-the-database"></a>Per aggiornare una riga nel database

1. Eseguire una query sul database per la riga da aggiornare.

2. Apportare le modifiche desiderate ai valori del membro nell'oggetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] risultante.

3. Inviare le modifiche al database.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene eseguita una query sul database per l'ordine N. 11000, quindi vengono modificati i valori di `ShipName` e `ShipVia` nell'oggetto `Order` risultante. Infine le modifiche a questi valori del membro vengono inviate al database come modifiche nelle colonne `ShipName` e `ShipVia`.

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
