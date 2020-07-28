---
title: Ildasm.exe (Disassembler IL)
description: Usare Ildasm.exe (disassembler IL), che accetta un file eseguibile di tipo PE contenente codice del linguaggio intermedio (IL) e crea un file di testo per la Ilasm.exe.
ms.date: 03/30/2017
helpviewer_keywords:
- PE files, MSIL Disassembler
- portable executable files, MSIL Disassembler
- Ildasm.exe
- MSIL Disassembler
- text files produced by MSIL Disassembler
- disassembling file for MSIL Assembler input
ms.assetid: db27f6b2-f1ec-499e-be3a-7eecf95ca42b
ms.openlocfilehash: 6f2611488e7f653783cab833ad47131978bf74aa
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166837"
---
# <a name="ildasmexe-il-disassembler"></a>Ildasm.exe (Disassembler IL)

Il disassembler IL è uno strumento complementare all'assembler IL (*Ilasm.exe*). *Ildasm.exe* accetta un file eseguibile portabile (PE) che contiene il codice del linguaggio intermedio (il) e crea un file di testo appropriato come input per *Ilasm.exe*.

Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).

Al prompt dei comandi digitare quanto segue:

## <a name="syntax"></a>Sintassi

```console
ildasm [options] [PEfilename] [options]
```

## <a name="parameters"></a>Parametri

Le opzioni seguenti sono disponibili per i file *. exe*, *. dll*, *. obj*, *. lib*e *. winmd* .

| Opzione | Descrizione |
| ------ | ----------- |
|**/out =**`filename`|Crea un file di output con `filename` specificato anziché visualizzare i risultati in un'interfaccia utente grafica.|
|**/rtf**|Genera l'output in formato RTF (Rich Text Format). Non valida con l'opzione **/text**.|
|**/Text**|Visualizza i risultati nella finestra della console, anziché in un'interfaccia utente grafica o in un file di output.|
|**/HTML**|Genera l'output in formato HTML. Valida solo con l'opzione **/output**.|
|**/?**|Visualizza la sintassi e le opzioni dei comandi dello strumento.|

Sono disponibili le seguenti opzioni aggiuntive per i file *. exe*, *. dll*e *. winmd* .

| Opzione | Descrizione |
| ------ | ----------- |
|**/bytes**|Mostra i byte effettivi, in formato esadecimale, come commenti di istruzioni.|
|**/caverbal**|Genera blob di attributi personalizzati in forma descrittiva. Il formato predefinito è quello binario.|
|**/linenum**|Include riferimenti alle righe di origine.|
|**/nobar**|Evita la visualizzazione della finestra popup contenente l'indicatore di stato del processo del disassembler.|
|**/noca**|Evita la generazione dell'output di attributi personalizzati.|
|**/Project**|Mostra i metadati come vengono visualizzati nel codice gestito invece che nel Windows Runtime nativo. Se `PEfilename` non è un file di metadati di Windows (con*estensione WinMD*), questa opzione non ha alcun effetto. Vedere [Supporto .NET Framework per applicazioni Windows Store e Windows Runtime](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).|
|**/pubonly**|Disassembla solo membri e tipi pubblici. Equivale a **/visibility:PUB**.|
|**/quoteallnames**|Racchiude tutti i nomi tra virgolette singole.|
|**/raweh**|Mostra le clausole di gestione delle eccezioni in formato non elaborato.|
|**/Source**|Mostra le righe di origine come commenti.|
|**/Tokens**|Mostra i token dei metadati di classi e membri.|
|**/visibility:** `vis`[+`vis`...]|Disassembla solo tipi o membri che presentano la visibilità specificata. Di seguito sono riportati i valori validi per `vis`:<br /><br /> **PUB** - Pubblico<br /><br /> **PRI** - Privato<br /><br /> **FAM** - Famiglia<br /><br /> **ASM** - Assembly<br /><br /> **FAA** - Famiglia e assembly<br /><br /> **FOA** - Famiglia o assembly<br /><br /> **PSC** - Ambito privato<br /><br /> Per le definizioni di questi modificatori di visibilità, vedere <xref:System.Reflection.MethodAttributes> e <xref:System.Reflection.TypeAttributes>.|

Le opzioni seguenti sono valide per i file *. exe*, *. dll*e *. winmd* solo per l'output di file o console.

| Opzione | Descrizione |
| ------ | ----------- |
|**/All**|Specifica una combinazione di opzioni **/header**, **/bytes**, **/stats**, **/classlist** e **/token**.|
|**/classlist**|Include un elenco di classi definite nel modulo.|
|**/Forward**|Utilizza la dichiarazione con prototipo della classe.|
|**/Headers**|Include nell'output le informazioni sull'intestazione del file.|
|**/Item:** `class` [**::** `member` [`(sig`]]|Disassembla quanto segue a seconda dell'argomento fornito:<br /><br /> -   Disassembla l'oggetto `class` specificato.<br />-   Disassembla l'oggetto `member` di `class` specificato.<br />-   Disassembla l'oggetto `member` di `class` con la firma `sig` specificata. Il formato di `sig` è il seguente:<br />     [`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)<br />     **Nota** Nelle versioni .NET Framework 1,0 e 1,1, `sig` deve essere seguito da una parentesi di chiusura: `(sig)` . A partire da .NET Framework 2.0 la parentesi di chiusura deve essere omessa: `(sig`.|
|**/noil**|Evita l'output del codice dell'assembly IL.|
|**/stats.**|Include le statistiche relative all'immagine.|
|**/typelist**|Genera l'elenco completo dei tipi per mantenere l'ordinamento dei tipi in un round trip.|
|**/Unicode**|Utilizza la codifica Unicode per l'output.|
|**/utf8**|Utilizza la codifica UTF-8 per l'output. ANSI è l'argomento predefinito.|

Le opzioni seguenti sono valide per i file *. exe*, *. dll*, *. obj*, *. lib*e *. winmd* solo per l'output di file o console.

| Opzione | Descrizione |
| ------ | ----------- |
|**/Metadata**[= `specifier` ]|Mostra i metadati, dove `specifier` è:<br /><br /> **MDHEADER**: visualizza le informazioni sull'intestazione e le dimensioni dei metadati.<br /><br /> **HEX**: visualizza le informazioni in esadecimali e in testo normale.<br /><br /> **CSV**: visualizza i conteggi di record e le dimensioni di heap.<br /><br /> **UNREX**: visualizza i riferimenti esterni non risolti.<br /><br /> **SCHEMA**: visualizza le informazioni sull'intestazione e lo schema dei metadati.<br /><br /> **RAW**: visualizza le tabelle di metadati non elaborate.<br /><br /> **HEAPS**: visualizza gli heap non elaborati.<br /><br /> **VALIDATE**: convalida la coerenza dei metadati.<br /><br /> È possibile specificare **/metadata** più volte, con valori diversi per `specifier`.|

Le opzioni seguenti sono valide per i file *. lib* solo per l'output di file o console.

| Opzione | Descrizione |
| ------ | ----------- |
|**/objectfile**=`filename`|Mostra i metadati di un singolo file oggetto nella libreria specificata.|

> [!NOTE]
> Tutte le opzioni per *Ildasm.exe* non fanno distinzione tra maiuscole e minuscole e vengono riconosciute dalle prime tre lettere. Ad esempio, **/quo** equivale a **/quoteallnames**. Le opzioni che specificano argomenti accettano i due punti (:) o un segno di uguale (=) come separatore tra l'opzione e l'argomento. **/output:** *nomefile*, ad esempio, equivale a **/output=** *nomefile*.

## <a name="remarks"></a>Osservazioni

*Ildasm.exe* opera solo su file PE su disco. e non su file installati nella Global Assembly Cache.

Il file di testo prodotto da *Ildasm.exe* può essere usato come input per l'assembler il (*Ilasm.exe*). Questo è utile, ad esempio, quando si compila codice in un linguaggio di programmazione che non supporta tutti gli attributi dei metadati del runtime. Dopo aver compilato il codice ed eseguito l'output tramite *Ildasm.exe*, il file di testo il risultante può essere modificato manualmente per aggiungere gli attributi mancanti. Sarà quindi possibile elaborare questo file di testo mediante l'assembler IL per produrre un file eseguibile finale.

> [!NOTE]
> Attualmente non è possibile avvalersi di questa tecnica con file PE contenenti codice nativo incorporato, ad esempio file PE prodotti da Visual C++.  

È possibile utilizzare la GUI predefinita del disassembler IL per visualizzare i metadati e il codice disassemblato di qualsiasi file PE esistente in una visualizzazione albero di tipo gerarchico. Per usare la GUI, digitare **ildasm** alla riga di comando senza specificare l'argomento *PEfilename* né alcuna opzione. Dal menu **file** è possibile passare al file PE che si desidera caricare in *Ildasm.exe*. Per salvare i metadati e il codice disassemblato visualizzati per il file PE selezionato, scegliere il comando **Dump** dal menu **File**. Per salvare solo la visualizzazione albero di tipo gerarchico, scegliere **Esegui il dump di TreeView** dal menu **File**. Per una guida dettagliata sul caricamento di un file in *Ildasm.exe* e sull'interpretazione dell'output, vedere l'esercitazione di *Ildasm.exe*, contenuta nella cartella Samples inclusa in Windows SDK.

Se si fornisce *Ildasm.exe* con un argomento *PEfilename* che contiene risorse incorporate, lo strumento produrrà più file di output: un file di testo che contiene il codice il e, per ogni risorsa gestita incorporata, un file con estensione resources prodotto usando il nome della risorsa dai metadati. Se una risorsa non gestita è incorporata in *PEfilename*, viene generato un file con estensione res usando il nome file specificato per l'output il **/output** opzione.

> [!NOTE]
> *Ildasm.exe* Mostra solo le descrizioni dei metadati per i file di input *. obj* e *. lib* . Il codice IL di questi tipi di file non viene disassemblato.

Per determinare se il file è gestito, è possibile eseguire *Ildasm.exe* an.exe o un file con *estensione dll* . Se il file non è gestito, verrà visualizzato un messaggio che comunica che il file non include alcuna intestazione Common Language Runtime valida e non può essere disassemblato. Se invece il file è gestito, l'operazione verrà eseguita correttamente.

## <a name="version-information"></a>Informazioni sulla versione

A partire da .NET Framework 4.5, *Ildasm.exe* gestisce un BLOB (oggetto binario di grandi dimensioni) di marshalling non riconosciuto visualizzando il contenuto binario non elaborato. Ad esempio, il codice seguente mostra come viene visualizzato un BLOB di marshalling generato da un programma C#:

```csharp
public void Test([MarshalAs((short)70)] int test) { }
```

```il
// IL from Ildasm.exe output
.method public hidebysig instance void Test(int32  marshal({ 46 }) test) cil managed
```

A partire da .NET Framework 4.5, *Ildasm.exe* visualizza gli attributi applicati alle implementazioni di interfaccia, come illustrato nel seguente estratto dell'output di *Ildasm.exe*:

```il
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

## <a name="examples"></a>Esempi

Il comando seguente consente di visualizzare i metadati e il codice disassemblato del file PE `MyHello.exe` nella GUI predefinita *Ildasm.exe* .

```console
ildasm myHello.exe
```

Il comando che segue disassembla il file `MyFile.exe` e archivia nel file *MyFile.il* il testo ottenuto per l'assembler IL.

```console
ildasm MyFile.exe /output:MyFile.il
```

Il comando che segue disassembla il file `MyFile.exe` e visualizza nella finestra della console il testo ottenuto per l'assembler IL.

```console
ildasm MyFile.exe /text
```

Se il file `MyApp.exe` contiene risorse incorporate gestite e non gestite, il comando seguente produrrà quattro file: *MyApp.il*, *MyApp.res*, *Icons.resources* e *Message.resources*:

```console
ildasm MyApp.exe /output:MyApp.il
```

Il comando seguente disassembla il metodo `MyMethod` della classe `MyClass` in `MyFile.exe` e visualizza l'output nella finestra della console.

```console
ildasm /item:MyClass::MyMethod MyFile.exe /text
```

Nell'esempio precedente potrebbero essere presenti più metodi denominati `MyMethod` con firme diverse. Il comando seguente disassembla il metodo di istanza `MyMethod` con il tipo restituito **void** e i tipi di parametri **int32** e **string**.

```console
ildasm /item:"MyClass::MyMethod(instance void(int32,string)" MyFile.exe /text
```

> [!NOTE]
> In .NET Framework versioni 1.0 e 1.1 la parentesi sinistra che segue il nome del metodo deve essere bilanciata da una parentesi destra dopo la firma: `MyMethod(instance void(int32))`. A partire da .NET Framework 2.0 la parentesi di chiusura deve essere omessa: `MyMethod(instance void(int32)`.

Per recuperare un metodo `static` (metodo`Shared` in Visual Basic), omettere la parola chiave `instance`. I tipi di classe che non sono tipi primitivi come `int32` e `string` devono includere lo spazio dei nomi e devono essere preceduti dalla parola chiave `class`. I tipi esterni devono essere preceduti dal nome della libreria tra parentesi quadre. Il comando che segue disassembla un metodo statico denominato `MyMethod` che ha un parametro di tipo <xref:System.AppDomain> e un tipo restituito di <xref:System.AppDomain>.

```console
ildasm /item:"MyClass::MyMethod(class [mscorlib]System.AppDomain(class [mscorlib]System.AppDomain)" MyFile.exe /text
```

Un tipo annidato deve essere preceduto dalla classe in cui è contenuto, delimitata da una barra. Se ad esempio nella classe `MyNamespace.MyClass` è contenuta una classe annidata denominata `NestedClass`, la classe annidata viene identificata come segue: `class MyNamespace.MyClass/NestedClass`.

## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Ilasm.exe (assembler IL)](ilasm-exe-il-assembler.md)
- [Processo di esecuzione gestita](../../standard/managed-execution-process.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
