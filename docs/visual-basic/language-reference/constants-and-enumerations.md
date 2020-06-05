---
title: Costanti ed enumerazioni
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 60cd1ddac9bca685ddc5778e7d289710245a183e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374486"
---
# <a name="constants-and-enumerations-visual-basic"></a>Costanti ed enumerazioni (Visual Basic)

Visual Basic fornisce una serie di costanti ed enumerazioni predefinite per gli sviluppatori. Le costanti archiviano i valori che rimangono costanti durante l'esecuzione di un'applicazione. Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.  
  
## <a name="constants"></a>Costanti  
  
### <a name="conditional-compilation-constants"></a>Costanti di compilazione condizionale  

 Nella tabella seguente sono elencate le costanti predefinite disponibili per la compilazione condizionale.  
  
|**Costante**|**Descrizione**|  
|---|---|  
|`CONFIG`|Stringa che corrisponde all'impostazione corrente della casella di **configurazione della soluzione attiva** nell' **Configuration Manager**.|  
|`DEBUG`|`Boolean`Valore che può essere impostato nella finestra di dialogo **Proprietà progetto** . Per impostazione predefinita, la configurazione di debug per un progetto definisce `DEBUG` . Quando `DEBUG` è definito, <xref:System.Diagnostics.Debug> i metodi della classe generano l'output nella finestra di **output** . Quando non è definito, <xref:System.Diagnostics.Debug> i metodi della classe non vengono compilati e non viene generato alcun output di debug.|  
|`TARGET`|Stringa che rappresenta il tipo di output per il progetto o l'impostazione **dell'opzione della** riga di comando. I valori possibili di `TARGET` sono:<br /><br /> -"winexe" per un'applicazione Windows.<br />-"exe" per un'applicazione console.<br />-"Library" per una libreria di classi.<br />-"Module" per un modulo.<br />-L'opzione **-target** può essere impostata in Visual Studio Integrated Development Environment. Per ulteriori informazioni, vedere [-target (Visual Basic)](../reference/command-line-compiler/target.md).|  
|`TRACE`|`Boolean`Valore che può essere impostato nella finestra di dialogo **Proprietà progetto** . Per impostazione predefinita, tutte le configurazioni per un progetto definiscono `TRACE` . Quando `TRACE` è definito, <xref:System.Diagnostics.Trace> i metodi della classe generano l'output nella finestra di **output** . Quando non è definito, <xref:System.Diagnostics.Trace> i metodi della classe non vengono compilati e non `Trace` viene generato alcun output.|  
|`VBC_VER`|Numero che rappresenta la versione di Visual Basic, in *Major*. formato *secondario* .|  
  
### <a name="print-and-display-constants"></a>Costanti di stampa e visualizzazione  

 Quando si chiamano funzioni di stampa e visualizzazione, è possibile usare le costanti seguenti nel codice al posto dei valori effettivi.  
  
|**Costante**|**Descrizione**|  
|---|---|  
|`vbCrLf`|Combinazione di caratteri ritorno a capo/avanzamento riga.|  
|`vbCr`|Carattere di ritorno a capo.|  
|`vbLf`|Carattere di avanzamento riga.|  
|`vbNewLine`|Carattere di nuova riga.|  
|`vbNullChar`|Carattere null.|  
|`vbNullString`|Non è uguale a una stringa di lunghezza zero (""); utilizzato per la chiamata di stored procedure esterne.|  
|`vbObjectError`|Numero di errore. I numeri errore definiti dall'utente devono essere maggiori di questo valore. Ad esempio:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carattere di tabulazione.|  
|`vbBack`|Carattere backspace.|  
|`vbFormFeed`|Non utilizzato in Microsoft Windows.|  
|`vbVerticalTab`|Non è utile in Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumerazioni  

 Nella tabella seguente vengono elencate e descritte le enumerazioni fornite da Visual Basic.  
  
|Enumerazione|Descrizione|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Indica lo stile della finestra da utilizzare per il programma richiamato quando viene chiamata la funzione <xref:Microsoft.VisualBasic.Interaction.Shell%2A>.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Indica come riprodurre i suoni quando vengono chiamati i metodi audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica il tipo di ruolo da controllare quando viene chiamato il metodo <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>.|  
|<xref:Microsoft.VisualBasic.CallType>|Indica il tipo di routine da richiamare quando viene chiamata la funzione <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Indica come confrontare le stringhe quando si chiamano funzioni di confronto.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Indica come visualizzare le date quando si chiama la funzione <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Indica come determinare e formattare gli intervalli di date quando si chiamano funzioni relative alle date.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Specifica le azioni da intraprendere quando si deve eliminare una directory contenente file o directory.|  
|<xref:Microsoft.VisualBasic.DueDate>|Indica le scadenze dei pagamenti quando vengono chiamati i metodi finanziari.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica se i campi di testo sono delimitati o a larghezza fissa.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Indica gli attributi file da utilizzare quando si chiamano funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica il primo giorno della settimana da utilizzare quando si chiamano funzioni relative alla data.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la prima settimana dell'anno da utilizzare quando si chiamano funzioni relative alla data.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Indica il pulsante su cui è stato fatto clic in una finestra di messaggio restituita dalla funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica i pulsanti da visualizzare durante la chiamata alla funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Indica la modalità di apertura del file quando si chiamano le funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Indica la modalità di apertura del file quando si chiamano le funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Indica la modalità di apertura del file quando si chiamano le funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Specifica se è necessario eliminare in modo permanente un file o posizionarlo nel Cestino.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Specifica se eseguire la ricerca in tutte le directory o solo in quelle di primo livello.|  
|<xref:Microsoft.VisualBasic.TriState>|Indica un `Boolean` valore o se è necessario utilizzare l'oggetto predefinito quando si chiamano le funzioni di formattazione dei numeri.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Specifica le operazioni da eseguire se l'utente fa clic su **Annulla** durante un'operazione.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Specifica se visualizzare o meno una finestra di dialogo di stato durante la copia, l'eliminazione o lo sviluppo di file o directory.|  
|<xref:Microsoft.VisualBasic.VariantType>|Indica il tipo di un oggetto Variant restituito dalla funzione <xref:Microsoft.VisualBasic.Information.VarType%2A>.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Indica il tipo di conversione da eseguire quando si chiama la funzione <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti al linguaggio Visual Basic](index.md)
- [Cenni preliminari sulle costanti](../programming-guide/language-features/constants-enums/constants-overview.md)
- [Cenni preliminari sulle enumerazioni](../programming-guide/language-features/constants-enums/enumerations-overview.md)
