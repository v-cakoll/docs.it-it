---
title: Costanti ed enumerazioni (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 33327a8d5e7ce7676ffda6245f3e4f9cccc8b1fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573309"
---
# <a name="constants-and-enumerations-visual-basic"></a>Costanti ed enumerazioni (Visual Basic)
Visual Basic fornisce un numero di costanti ed enumerazioni per gli sviluppatori predefinite. Archiviano i valori che rimangono costanti durante l'esecuzione di un'applicazione. Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.  
  
## <a name="constants"></a>Costanti  
  
### <a name="conditional-compilation-constants"></a>Costanti di compilazione condizionale  
 Nella tabella seguente sono elencate le costanti predefinite disponibili per la compilazione condizionale.  
  
|**Costante**|**Descrizione**|  
|---|---|  
|`CONFIG`|Stringa che corrisponde all'impostazione corrente del **configurazione soluzione attiva** nella casella il **Configuration Manager**.|  
|`DEBUG`|Oggetto `Boolean` valore che può essere impostata nel **le proprietà del progetto** nella finestra di dialogo. Per impostazione predefinita, la configurazione di Debug per un progetto definisce `DEBUG`. Quando `DEBUG` è definito <xref:System.Diagnostics.Debug> metodi della classe generano l'output per il **Output** finestra. Quando non è definito, <xref:System.Diagnostics.Debug> metodi della classe non vengono compilati e viene generato alcun output di Debug.|  
|`TARGET`|Stringa che rappresenta il tipo di output per il progetto o l'impostazione della riga di comando **/target** opzione. I valori possibili di `TARGET` sono:<br /><br /> -"winexe" per un'applicazione Windows.<br />-"exe" per un'applicazione console.<br />-"library" per una libreria di classi.<br />-"modulo" per un modulo.<br />-il **/target** opzione può essere impostata nell'ambiente di sviluppo integrato di Visual Studio. Per altre informazioni, vedere [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Oggetto `Boolean` valore che può essere impostata nel **le proprietà del progetto** nella finestra di dialogo. Per impostazione predefinita, tutte le configurazioni per un progetto definiscono `TRACE`. Quando `TRACE` è definito <xref:System.Diagnostics.Trace> metodi della classe generano l'output per il **Output** finestra. Quando non è definito, <xref:System.Diagnostics.Trace> classe i metodi non vengono compilati e nessun `Trace` output viene generato.|  
|`VBC_VER`|Numero che rappresenta la versione di Visual Basic, in *principali*. *minori* formato. Il numero di versione per [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] è 8.0.|  
  
### <a name="print-and-display-constants"></a>Costanti di visualizzazione e stampa  
 Quando si chiama stampa e visualizzare le funzioni, è possibile usare le seguenti costanti nel codice al posto dei valori effettivi.  
  
|**Costante**|**Descrizione**|  
|---|---|  
|`vbCrLf`|Combinazione a capo/avanzamento riga.|  
|`vbCr`|Carattere di ritorno a capo.|  
|`vbLf`|Carattere di avanzamento riga.|  
|`vbNewLine`|Carattere di nuova riga.|  
|`vbNullChar`|Carattere null.|  
|`vbNullString`|Non equivale a una stringa di lunghezza zero (""); usato per chiamare routine esterne.|  
|`vbObjectError`|Numero errore. I numeri di errore definiti dall'utente devono essere maggiori di questo valore. Ad esempio:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Carattere di tabulazione.|  
|`vbBack`|Carattere backspace.|  
|`vbFormFeed`|Non utilizzato in Microsoft Windows.|  
|`vbVerticalTab`|Non è utile in Microsoft Windows.|  
  
## <a name="enumerations"></a>Enumerazioni  
 Nella tabella seguente elenca e descrive le enumerazioni fornite da Visual Basic.  
  
|Enumerazione|Descrizione|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Indica lo stile della finestra da utilizzare per il programma richiamato quando si chiama il <xref:Microsoft.VisualBasic.Interaction.Shell%2A> (funzione).|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Indica come riprodurre suoni quando si chiamano metodi audio.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Indica il tipo di ruolo per controllare quando viene chiamato il <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> (metodo).|  
|<xref:Microsoft.VisualBasic.CallType>|Indica il tipo di routine da richiamare quando si chiama il <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> (funzione).|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Indica come confrontare le stringhe quando si chiamano le funzioni di confronto.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Indica come visualizzare le date quando si chiama il <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> (funzione).|  
|<xref:Microsoft.VisualBasic.DateInterval>|Indica come determinare e formattare gli intervalli di date quando si chiamano funzioni relative alle date.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Specifica le azioni da intraprendere quando una directory che deve essere eliminato contiene file o directory.|  
|<xref:Microsoft.VisualBasic.DueDate>|Indica le scadenze dei pagamenti quando si chiamano i metodi finanziari.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Indica se i campi di testo sono delimitati o a larghezza fissa.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Indica gli attributi di file da utilizzare quando si chiamano funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Indica il primo giorno della settimana da utilizzare quando si chiamano funzioni relative alle date.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Indica la prima settimana dell'anno da utilizzare quando si chiamano funzioni relative alle date.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Indica il pulsante su cui è stato fatto clic in una finestra di messaggio restituita dalla funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Indica i pulsanti da visualizzare durante la chiamata alla funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Indica come aprire un file quando si chiamano funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Indica come aprire un file quando si chiamano funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Indica come aprire un file quando si chiamano funzioni di accesso ai file.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Specifica se un file deve essere eliminato in modo permanente o inserito nel Cestino.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Specifica se la ricerca in tutti o solo le directory di primo livello.|  
|<xref:Microsoft.VisualBasic.TriState>|Indica un `Boolean` valore o se il valore predefinito deve essere usato quando si chiamano funzioni di formattazione dei numeri.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Specifica quale deve essere eseguita se l'utente fa clic **annullare** durante un'operazione.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Specifica se visualizzare una finestra di dialogo di avanzamento durante la copia, eliminazione o spostamento di file o directory o meno.|  
|<xref:Microsoft.VisualBasic.VariantType>|Indica il tipo di un oggetto variant restituito dal <xref:Microsoft.VisualBasic.Information.VarType%2A> (funzione).|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Indica il tipo di conversione da eseguire quando si chiama la funzione <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>Vedere anche
- [Riferimenti per il linguaggio Visual Basic](../../visual-basic/language-reference/index.md)
- [Visual Basic](../../visual-basic/index.md)
- [Cenni preliminari sulle costanti](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Cenni preliminari sulle enumerazioni](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
