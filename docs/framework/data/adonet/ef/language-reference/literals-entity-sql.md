---
title: Valori letterali (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
ms.openlocfilehash: bff9b1907d3424dc2e3df80480b6ab12f5ab9261
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209775"
---
# <a name="literals-entity-sql"></a>Valori letterali (Entity SQL)
In questo argomento viene descritto il supporto [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per i valori letterali.  
  
## <a name="null"></a>Null  
 Il valore letterale Null viene usato per rappresentare il valore Null per qualsiasi tipo. Un valore letterale Null è compatibile con qualsiasi tipo.  
  
 I valori Null tipizzati possono essere creati tramite cast su un valore letterale Null. Per altre informazioni, vedere [CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md).  
  
 Per le regole sulla posizione in cui libero a mobile valori letterali null mobili possono essere usati, vedere [valori letterali Null e inferenza del tipo](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md).  
  
## <a name="boolean"></a>Booleano  
 I valori letterali Boolean sono rappresentati dalle parole chiave `true` e `false`.  
  
## <a name="integer"></a>Integer  
 I valori letterali Integer possono essere di tipo <xref:System.Int32> o <xref:System.Int64>. Un valore letterale <xref:System.Int32> è costituito da una serie di caratteri numerici. Un valore letterale <xref:System.Int64> è costituito da una serie di caratteri numerici seguiti da una L maiuscola.  
  
## <a name="decimal"></a>Decimale  
 Un numero a virgola fissa, o decimale, è costituito da una serie di caratteri numerici, un separatore decimale e un'altra serie di caratteri numerici seguiti da una "M" maiuscola.  
  
## <a name="float-double"></a>Float, Double  
 Un numero a virgola mobile con precisione doppia è costituito da una serie di caratteri numerici, un separatore decimale e un'altra serie di caratteri numerici che possono essere seguiti da un esponente. Un numero a virgola mobile con precisione singola, o float, è costituito dalla sintassi di un numero a virgola mobile con precisione doppia, seguita dalla f minuscola.  
  
## <a name="string"></a>Stringa  
 Una stringa è una serie di caratteri racchiusi tra virgolette. Le virgolette possono essere entrambe singole (`'`) o entrambe doppie ("). I valori letterali carattere di tipo String possono essere Unicode o non Unicode. Per dichiarare un valore letterale carattere di tipo String come Unicode, anteporre una "N" maiuscola al valore. Per impostazione predefinita, i valori letterali carattere di tipo String sono non Unicode. Non possono essere presenti spazi tra la N e il payload del valore letterale di tipo String e la N deve essere maiuscola.  
  
```  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a>DateTime  
 Un valore letterale di tipo DateTime è indipendente dalle impostazioni locali ed è composto da una parte relativa alla data e da una parte relativa all'ora. Entrambe queste parti sono obbligatorie e non vi sono valori predefiniti.  
  
 La parte della data deve essere nel formato: `YYYY` - `MM` - `DD`, dove `YYYY` è un valore dell'anno a quattro cifre compreso tra 0001 e 9999 `MM` è il mese compreso tra 1 e 12 e `DD` è il valore del giorno che sono valido per il mese specificato `MM`.  
  
 La parte relativa all'ora deve essere nel formato `HH`:`MM`[:`SS`[.fffffff]], dove `HH` è il valore dell'ora compreso tra 0 e 23, `MM` è il valore dei minuti compreso tra 0 e 59, `SS` è il valore dei secondi compreso tra 0 e 59 e fffffff è il valore dei secondi frazionari compreso tra 0 e 9999999. Tutti gli intervalli includono il primo e l'ultimo valore. I secondi frazionari sono facoltativi. I secondi sono facoltativi, a meno che non vengano specificati i secondi frazionari. In questo caso, i secondi sono obbligatori. Quando i secondi o i secondi frazionari non sono specificati, viene usato il valore predefinito zero.  
  
 Tra il simbolo DATETIME e il payload con valore letterale può essere presente un numero qualsiasi di spazi ma non possono essere presenti nuove righe.  
  
```  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a>Ora  
 Un valore letterale Time è indipendente dalle impostazioni locali ed è composto solo da una parte relativa all'ora. La parte relativa all'ora è obbligatoria e non è previsto alcun valore predefinito. Questa parte deve essere nel formato HH:MM[:SS[.fffffff]], dove HH è il valore dell'ora compreso tra 0 e 23, MM è il valore dei minuti compreso tra 0 e 59, SS è il valore dei secondi compreso tra 0 e 59 e fffffff è il valore della frazione di secondo compreso tra 0 e 9999999. Tutti gli intervalli includono il primo e l'ultimo valore. I secondi frazionari sono facoltativi. I secondi sono facoltativi, a meno che non vengano specificati i secondi frazionari. In questo caso, i secondi sono obbligatori. Quando i secondi o le frazioni di secondo non sono specificati, viene usato il valore predefinito zero.  
  
 Tra il simbolo TIME e il payload con valore letterale può essere presente un numero qualsiasi di spazi ma non possono essere presenti nuove righe.  
  
```  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a>DateTimeOffset  
 Un valore letterale di tipo DateTimeOffset è indipendente dalle impostazioni locali ed è composto da una parte relativa alla data, una parte relativa all'ora e una parte relativa all'offset. Tutte e tre le parti sono obbligatorie e non vi sono valori predefiniti. La parte relativa alla data deve essere nel formato YYYY-MM-DD, dove YYYY è un valore dell'anno a quattro cifre compreso tra 0001 e 9999, MM è il mese compreso tra 1 e 12, e DD è il valore del giorno valido per il mese specificato. La parte relativa all'ora deve essere nel formato HH:MM[:SS[.fffffff]], dove HH è il valore dell'ora compreso tra 0 e 23, MM è il valore dei minuti compreso tra 0 e 59, SS è il valore dei secondi compreso tra 0 e 59 e fffffff è il valore dei secondi frazionari compreso tra 0 e 9999999. Tutti gli intervalli includono il primo e l'ultimo valore. I secondi frazionari sono facoltativi. I secondi sono facoltativi, a meno che non vengano specificati i secondi frazionari. In questo caso, i secondi sono obbligatori. Quando i secondi o le frazioni di secondo non sono specificati, viene usato il valore predefinito zero. La parte relativa all'offset deve essere nel formato {+&#124;-} hh: mm, dove HH e MM hanno lo stesso significato come la parte dell'ora. L'intervallo dell'offset deve tuttavia essere compreso tra -14:00 e + 14:00.  
  
 Tra il simbolo DATETIMEOFFSET e il payload con valore letterale può essere presente un numero qualsiasi di spazi ma non possono essere presenti nuove righe.  
  
```  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
>  Un valore letterale Entity SQL valido può non rientrare negli intervalli supportati per CLR o per l'origine dati. Ciò potrebbe generare un'eccezione.  
  
## <a name="binary"></a>Binario  
 Un valore letterale stringa di tipo Binary è una sequenza di cifre esadecimali delimitata da virgolette singole che seguono la parola chiave binary oppure il simbolo rapido `X` o `x`. Per il simbolo rapido `X` non viene fatta distinzione tra maiuscole e minuscole. Tra la parola chiave `binary` e il valore della stringa binaria sono consentiti zero o più spazi.  
  
 Anche per i caratteri esadecimali non viene fatta distinzione tra maiuscole e minuscole. Se il valore letterale è composto da un numero dispari di cifre esadecimali, verrà allineato alla cifra esadecimale pari successiva anteponendo una cifra zero esadecimale. Non vi sono limiti formali alle dimensioni della stringa binaria.  
  
```  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a>GUID  
 Un valore letterale `GUID` rappresenta un identificatore univoco globale. Si tratta di una sequenza formata dalla parola chiave `GUID` seguito da cifre esadecimali nel formato noto come *registro* formato: 4-4-4-8-12 racchiuso tra virgolette singole. Per le cifre esadecimali non viene fatta distinzione tra maiuscole e minuscole.  
  
 Tra il simbolo GUID e il payload con valore letterale può essere presente un numero qualsiasi di spazi ma non possono essere presenti nuove righe.  
  
```  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
