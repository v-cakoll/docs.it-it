---
title: 'Procedura: utilizzare argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 3fce8a30e9ed663f06fa04c462fc1e1fd249d27a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321873"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Procedura: utilizzare argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C#)
Gli argomenti denominati e gli argomenti facoltativi, introdotti in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], migliorano la praticità, la flessibilità e la leggibilità nella programmazione C#. Queste funzionalità, poi, semplificano notevolmente l'accesso alle interfacce COM, quali le API di automazione di Microsoft Office.  
  
 Nell'esempio seguente, il metodo [ConvertToTable](https://msdn.microsoft.com/library/bb216993.aspx) dispone di sedici parametri che rappresentano le caratteristiche di una tabella, ad esempio il numero di colonne e di righe, la formattazione, i bordi, i tipi di carattere e i colori. I sedici parametri sono tutti facoltativi, perché nella maggior parte dei casi non si vogliono specificare particolari valori per tutti. Senza gli argomenti denominati e facoltativi, tuttavia, è necessario specificare un valore o un valore di segnaposto per ogni parametro. Con gli argomenti denominati e facoltativi si specificano valori solo per i parametri obbligatori per il progetto.  
  
 Per eseguire queste procedure, Microsoft Office Word deve essere installato.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a>Per creare un nuovo progetto di applicazione console  
  
1.  Avviare Visual Studio.  
  
2.  Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.  
  
3.  Nel riquadro **Categorie di modelli** espandere **Visual C#** e quindi fare clic su **Windows**.  
  
4.  Verificare che nella parte superiore del riquadro **Modelli** sia visualizzato **.NET Framework 4** nella casella **Framework di destinazione**.  
  
5.  Nel riquadro **Modelli** fare clic su **Applicazione console**.  
  
6.  Digitare un nome per il progetto nel campo **Nome**.  
  
7.  Fare clic su **OK**.  
  
     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.  
  
### <a name="to-add-a-reference"></a>Per aggiungere un riferimento  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nome del progetto e quindi scegliere **Aggiungi riferimento**. Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.  
  
2.  Nella pagina **.NET** selezionare **Microsoft.Office.Interop.Word** nell'elenco **Nome componente**.  
  
3.  Fare clic su **OK**.  
  
### <a name="to-add-necessary-using-directives"></a>Per aggiungere le direttive using necessarie  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file **Program.cs** e quindi fare clic su **Visualizza codice**.  
  
2.  Aggiungere le seguenti direttive `using` all'inizio del file di codice.  
  
     [!code-csharp[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### <a name="to-display-text-in-a-word-document"></a>Per visualizzare il testo in un documento di Word  
  
1.  Nella classe `Program` in Program.cs aggiungere il metodo seguente per creare un'applicazione di Word e un documento di Word. Il metodo [Add](https://msdn.microsoft.com/library/microsoft.office.interop.word.documents.add.aspx) dispone di quattro parametri facoltativi. Questo esempio usa i relativi valori predefiniti. Non sono pertanto necessari argomenti nell'istruzione di chiamata.  
  
     [!code-csharp[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  Aggiungere il codice seguente alla fine del metodo per definire il punto in cui visualizzare del testo nel documento e quale testo visualizzare.  
  
     [!code-csharp[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### <a name="to-run-the-application"></a>Per eseguire l'applicazione  
  
1.  Aggiungere a Main l'istruzione riportata di seguito.  
  
     [!code-csharp[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  Premere CTRL+F5 per eseguire il progetto. Verrà visualizzato un documento di Word contenente il testo specificato.  
  
### <a name="to-change-the-text-to-a-table"></a>Per convertire il testo in una tabella  
  
1.  Usare il metodo `ConvertToTable` per racchiudere il testo in una tabella. Il metodo ha 16 parametri facoltativi. IntelliSense racchiude tra parentesi quadre i parametri facoltativi, come mostrato nell'immagine seguente.  
  
     ![Elenco dei parametri del metodo ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")  
Parametri di ConvertToTable  
  
     Gli argomenti denominati e facoltativi consentono di specificare valori esclusivamente per i parametri che si vogliono modificare. Aggiungere il codice seguente alla fine del metodo `DisplayInWord` per creare una tabella semplice. L'argomento indica che le virgole nella stringa di testo in `range` separano le celle della tabella.  
  
     [!code-csharp[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     Nelle versioni precedenti di C# la chiamata a `ConvertToTable` richiede un argomento di riferimento per ogni parametro, come illustrato nel codice seguente.  
  
     [!code-csharp[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  Premere CTRL+F5 per eseguire il progetto.  
  
### <a name="to-experiment-with-other-parameters"></a>Per provare a usare altri parametri  
  
1.  Per modificare la tabella in modo che contenga una colonna e tre righe, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere CTRL+F5.  
  
     [!code-csharp[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  Per specificare un formato predefinito per la tabella, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere CTRL+F5. Il formato può corrispondere a qualsiasi costante [WdTableFormat](https://msdn.microsoft.com/library/microsoft.office.interop.word.wdtableformat.aspx).  
  
     [!code-csharp[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente include l'esempio completo.  
  
 [!code-csharp[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Argomenti denominati e facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
