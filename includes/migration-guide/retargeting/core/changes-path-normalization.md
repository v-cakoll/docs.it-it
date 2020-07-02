---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614464"
---
### <a name="changes-in-path-normalization"></a>Modifica nella normalizzazione del percorso

#### <a name="details"></a>Dettagli

A partire dalle app destinate a .NET Framework 4.6.2, il modo in cui il runtime normalizza i percorsi è cambiato. La normalizzazione di un percorso implica la modifica della stringa che identifica un percorso o un file in modo che sia conforme a un percorso valido nel sistema operativo di destinazione. In genere, la normalizzazione implica:

- La conversione in forma canonica dei separatori di directory e dei componenti.
- L'applicazione della directory corrente in un percorso relativo.
- La valutazione della directory relativa (.) o della directory padre (..) in un percorso.
- La rimozione di caratteri specificati.
Le modifiche seguenti per la normalizzazione del percorso sono abilitate per impostazione predefinita a partire dalle app destinate a .NET Framework 4.6.2:
  - Il runtime viene rinviato alla funzione [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) del sistema operativo per normalizzare i percorsi.
- La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).
- Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib.dll, `\\?\`.
- Il runtime non convalida i percorsi di sintassi del dispositivo.
- È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.
Queste modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere a percorsi in precedenza inaccessibili. Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.

#### <a name="suggestion"></a>Suggerimento

Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione su .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6.2       |
| Type    | Ridestinazione |
