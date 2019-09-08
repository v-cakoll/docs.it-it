---
title: 'Procedura: Convalidare file di mapping esterni e DBML'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: b5901705ac7c0692025ff1f4a4b78f976d62176d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793048"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Procedura: Convalidare file di mapping esterni e DBML

I file di mapping esterno e i file con estensione dbml modificati devono essere convalidati in base alle rispettive definizioni dello schema. Questo argomento fornisce agli utenti di Visual Studio i passaggi per implementare il processo di convalida.

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a>Per convalidare un file con estensione dbml o un file XML

1. Scegliere **Apri**dal menu **file** di Visual Studio, quindi fare clic su **file**.

2. Nella finestra di dialogo **Apri file** fare clic sul file con estensione dbml o di mapping XML che si desidera convalidare.

    Il file verrà aperto nell' **editor XML**.

3. Fare clic con il pulsante destro del mouse sulla finestra, quindi scegliere **Proprietà**.

4. Nella finestra **Proprietà** fare clic sui puntini di sospensione per la proprietà **schemi** .

    Verrà visualizzata la finestra di dialogo **schemi XML** .

5. Notare la definizione dello schema adatta allo scopo.

    - DbmlSchema.xsd è la definizione dello schema per la convalida di un file dbml. Per altre informazioni, vedere [generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md).

    - LinqToSqlMapping.xsd è la definizione dello schema per la convalida di un file di mapping XML esterno. Per ulteriori informazioni, vedere [mapping esterno](external-mapping.md).

6. Nella colonna **utilizza** della riga definizione dello schema desiderata fare clic per aprire la casella di riepilogo a discesa e quindi fare clic su **utilizza questo schema**.

    Il file di definizione dello schema è ora associato al file di mapping DBML o XML.

    Assicurarsi che non siano selezionate altre definizioni dello schema.

7. Scegliere **Elenco errori**dal menu **Visualizza** .

    Determinare se sono stati generati errori, avvisi o messaggi. In caso contrario, il file XML è valido per la definizione dello schema.

## <a name="alternate-method-for-supplying-schema-definition"></a>Metodo alternativo per fornire la definizione dello schema

Se per qualche motivo il file xsd appropriato non viene visualizzato nella finestra di dialogo **XML Schema** , è possibile scaricare il file con estensione XSD da un argomento della guida. La procedura seguente consente di salvare il file scaricato nel formato Unicode richiesto dall'editor XML di Visual Studio.

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>Per copiare un file di definizione dello schema da un argomento della Guida

1. Individuare l'argomento della Guida che contiene la definizione dello schema descritta in questo argomento.

    - Per i file con estensione dbml, vedere [generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md).

    - Per i file di mapping esterni, vedere [mapping esterno](external-mapping.md).

2. Fare clic su **Copia codice** per copiare il file di codice negli Appunti.

3. Avviare il Blocco note per creare un nuovo file.

4. Incollare il codice dagli Appunti nel file del Blocco note.

5. Scegliere **Salva con nome**dal menu **file** del blocco note.

6. Nella casella **codifica** selezionare **Unicode**.

    > [!IMPORTANT]
    > Questa selezione assicura che il file di testo sia preceduto dal marcatore dell'ordine di byte Unicode 16 (`FFFE`).

7. Nella casella **nome file** creare un nome file con estensione XSD.

## <a name="see-also"></a>Vedere anche

- [Riferimento](reference.md)
