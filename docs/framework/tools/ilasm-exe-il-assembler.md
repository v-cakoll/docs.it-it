---
title: Ilasm.exe (Assembler IL)
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: cb995e78e534048043886070536ef0dd0a45c057
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73105096"
---
# <a name="ilasmexe-il-assembler"></a>Ilasm.exe (Assembler IL)

L'assembler IL genera un file eseguibile di tipo PE dal linguaggio intermedio (IL). Per ulteriori informazioni su IL, vedere [processo di esecuzione gestita](../../standard/managed-execution-process.md). È possibile eseguire l'eseguibile risultante, che contiene il e i metadati necessari, per determinare se il linguaggio il viene eseguito come previsto.

Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).

Al prompt dei comandi digitare quanto segue:

## <a name="syntax"></a>Sintassi

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a>Parametri

| Argomento | Descrizione |
| -------- | ----------- |
|`filename`|Nome del file di origine .il. Questo file è formato da direttive di dichiarazione di metadati e istruzioni IL simboliche. È possibile fornire più argomenti di file di origine per produrre un unico file PE con *Ilasm. exe*. **Nota:** Verificare che l'ultima riga di codice nel file di origine con estensione il includa uno spazio vuoto finale o un carattere di fine riga.|

| Opzione | Description |
| ------ | ----------- |
|**/32bitpreferred**|Crea un'immagine con preferenza per i 32 bit (PE32).|
|**/Alignment:**`integer`|Imposta FileAlignment sul valore specificato da `integer` nell'intestazione NT facoltativa. Se la direttiva IL .alignment è specificata nel file, questa opzione ne esegue l'override.|
|**/appcontainer**|Produce un file *. dll* o *. exe* che viene eseguito nel contenitore dell'app Windows come output.|
|**/arm**|Specifica Advanced RISC Machine (ARM) come processore di destinazione.<br /><br /> Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/32bitpreferred**.|
|**/base:**`integer`|Imposta ImageBase sul valore specificato da `integer` nell'intestazione NT facoltativa. Se la direttiva IL .imagebase è specificata nel file, questa opzione ne esegue l'override.|
|**/clock**|Misura e segnala i seguenti tempi di compilazione in millisecondi per il file di origine .il specificato:<br /><br /> **Total Run**: tempo totale impiegato per l'esecuzione di tutte le operazioni specifiche che seguono.<br /><br /> **Startup**: caricamento e apertura del file.<br /><br /> **Emitting MD**: emissione di metadati.<br /><br /> **Ref to Def Resolution**: risoluzione dei riferimenti nelle definizioni nel file.<br /><br /> **CEE File Generation**: generazione dell'immagine del file in memoria.<br /><br /> **PE File Writing**: scrittura dell'immagine in un file PE.|
|**/debug**[:**IMPL**&#124;**OPT**]|Include informazioni di debug (nomi di variabili locali e di argomenti e numeri di riga). Crea un file PDB.<br /><br /> Se si specifica **/debug** senza altri valori, viene disabilitata l'ottimizzazione JIT e vengono utilizzati i punti di sequenza dal file PDB.<br /><br /> **IMPL** disabilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.<br /><br /> **OPT** abilita l'ottimizzazione JIT e utilizza punti di sequenza impliciti.|
|**/dll**|Produce un file con *estensione dll* come output.|
|**/enc:**`file`|Crea file differenziali di Modifica e continuazione a partire dal file di origine specificato.<br /><br /> Questo argomento è esclusivamente per utilizzo didattico e non è supportato per un utilizzo commerciale.|
|**/exe**|Produce un file eseguibile come output. Questa è la modalità predefinita.|
|**/flags:**`integer`|Imposta ImageFlags sul valore specificato da `integer` nell'intestazione Common Language Runtime. Se la direttiva IL .corflags è specificata nel file, questa opzione ne esegue l'override. Per un elenco di valori validi per *integer*, vedere CorHdr.h, COMIMAGE_FLAGS.|
|**/fold**|Raggruppa corpi di metodo identici in uno solo.|
|/**highentropyva**|Genera in output un file eseguibile che supporta ASLR (Address Space Layout Randomization) a entropia elevata. Impostazione predefinita per **/appcontainer**.|
|**/include:**`includePath`|Imposta un percorso per la ricerca di file inclusi con `#include`.|
|**/itanium**|Specifica Intel Itanium come processore di destinazione.<br /><br /> Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.|
|**/Key:**`keyFile`|Compila `filename` con una firma sicura usando la chiave privata contenuta in `keyFile`.|
|**/Key** @`keySource`|Compila `filename` con una firma sicura usando la chiave privata prodotta in `keySource`.|
|**/Listing**|Produce un file di elenco sull'output standard. Se si omette questa opzione, non verrà prodotto alcun file di elenco.<br /><br /> Questo parametro non è supportato in .NET Framework 2.0 o versione successiva.|
|**/MDV:**`versionString`|Imposta la stringa di versione dei metadati.|
|**/MSV:** `major`.`minor`|Imposta la versione del flusso di metadati, dove `major` e `minor` sono numeri interi.|
|**/noautoinherit**|Disabilita l'ereditarietà predefinita da <xref:System.Object> quando non è specificata alcuna classe base.|
|**/nocorstub**|Elimina la generazione dello stub CORExeMain.|
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|
|**/output:**`file.ext`|Specifica il nome e l'estensione del file di output. Per impostazione predefinita, il nome del file di output corrisponde al nome del primo file di origine. L'estensione predefinita è *. exe*. Se si specifica l'opzione **/dll** , l'estensione predefinita sarà *. dll*. **Nota:** Se si specifica **/output**: myfile. dll, non viene impostata l'opzione **/dll** . Se non si specifica **/dll**, il risultato sarà un file eseguibile denominato *MyFile. dll*.|
|**/Optimize**|Ottimizza le istruzioni long convertendole in short. Ad esempio, `br` viene convertito in `br.s`.|
|**/pe64**|Crea un'immagine a 64 bit (PE32+).<br /><br /> Se non è specificato il processore di destinazione, l'impostazione predefinita è `/itanium`.|
|**/PDB**|Crea un file PDB senza abilitare la traccia delle informazioni di debug.|
|**/quiet**|Specifica la modalità non interattiva. Non visualizza informazioni sullo stato dell'assembly.|
|**/Resource:**`file.res`|Include il file di risorse specificato \*nel formato res nel file con *estensione exe* o *dll* risultante. È possibile specificare un unico file .res con l'opzione **/resource** .|
|**/ssver:** `int`.`int`|Imposta il numero di versione del sottosistema nell'intestazione NT facoltativa. Per **/appcontainer** e **/arm** il numero minimo di versione è 6.02.|
|**/stack:**`stackSize`|Imposta su `stackSize`il valore di SizeOfStackReserve nell'intestazione NT facoltativa.|
|**/stripreloc**|Specifica che non sono necessarie rilocazioni di base.|
|**/SUBSYSTEM:**`integer`|Imposta il sottosistema sul valore specificato da `integer` nell'intestazione NT facoltativa. Se la direttiva IL .subsystem è specificata nel file, questo comando ne esegue l'override. Per un elenco di valori validi per `integer`, vedere winnt.h, IMAGE_SUBSYSTEM.|
|**/x64**|Specifica un processore AMD a 64 bit come processore di destinazione.<br /><br /> Se non viene specificato il numero di bit dell'immagine, viene utilizzata l'impostazione predefinita **/pe64**.|
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|

> [!NOTE]
> Tutte le opzioni per *Ilasm. exe* non fanno distinzione tra maiuscole e minuscole e vengono riconosciute dalle prime tre lettere. Ad esempio, **/LIS** è equivalente a **/Listing** e **/res**: myresfile. res è equivalente a **/Resource**: myresfile. res. Le opzioni che specificano gli argomenti accettano due punti (:) o un segno di uguale (=) come separatore tra l'opzione e l'argomento. Ad esempio, **/output**:*file. ext* equivale a **/output**=*file. ext*.

## <a name="remarks"></a>Osservazioni

L'assembler IL consente ai fornitori di strumenti di progettare e implementare generatori IL. Con *Ilasm. exe*, gli sviluppatori di strumenti e compilatori possono concentrarsi su il e sulla generazione di metadati senza preoccuparsi di emettere il nel formato di file PE.

Analogamente ad altri compilatori destinati al runtime, ad esempio C# e Visual Basic, *Ilasm. exe* non produce file oggetto intermedi e non richiede una fase di collegamento per creare un file PE.

L'assembler IL è in grado di esprimere tutte le funzionalità esistenti per IL e i metadati dei linguaggi di programmazione destinati al runtime. In questo modo il codice gestito scritto in uno qualsiasi di questi linguaggi di programmazione può essere espresso in modo adeguato nell'assembler IL e compilato con *Ilasm. exe*.

> [!NOTE]
> È possibile che la compilazione abbia esito negativo se nell'ultima riga di codice del file di origine con estensione il non è presente uno spazio vuoto finale o un carattere di fine riga.

È possibile utilizzare *Ilasm. exe* insieme allo strumento complementare Ildasm. [*exe*](ildasm-exe-il-disassembler.md). *Ildasm. exe* accetta un file PE che contiene IL codice il e crea un file di testo adatto come input per *Ilasm. exe*. Questo è utile, ad esempio, quando si compila codice in un linguaggio di programmazione che non supporta tutti gli attributi dei metadati del runtime. Dopo aver compilato il codice ed eseguito l'output tramite *Ildasm. exe*, il file di testo il risultante può essere modificato manualmente per aggiungere gli attributi mancanti. È quindi possibile eseguire questo file di testo tramite *Ilasm. exe* per produrre un file eseguibile finale.

È inoltre possibile ricorrere a questa tecnica per produrre un unico file PE sulla base di più file PE generati da diversi compilatori.

> [!NOTE]
> Attualmente non è possibile avvalersi di questa tecnica con file PE contenenti codice nativo incorporato, ad esempio file PE prodotti da Visual C++.

Per fare in modo che questo utilizzo combinato di *Ildasm. exe* e *Ilasm. exe* sia il più accurato possibile, per impostazione predefinita l'assembler non sostituisce le codifiche brevi per quelle lunghe che potrebbero essere state scritte nelle origini il (o che potrebbero essere emesse da un altro compilatore). Utilizzare l'opzione **/optimize** per sostituire le codifiche short quando possibile.

> [!NOTE]
> *Ildasm. exe* opera solo su file su disco. e non su file installati nella Global Assembly Cache.

Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.

## <a name="version-information"></a>Informazioni sulla versione

A partire da .NET Framework 4.5, è possibile associare un attributo personalizzato a un'implementazione di interfaccia usando codice analogo al seguente:

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

A partire da .NET Framework 4.5, è possibile specificare un BLOB (oggetto binario di grandi dimensioni) marshalling arbitrario usando la relativa rappresentazione binaria non elaborata, come illustrato nel codice seguente:

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

Per altre informazioni sulla grammatica di IL, vedere il file asmparse.grammar in Windows SDK.

## <a name="examples"></a>Esempi

Il comando che segue assembla il file IL *myTestFile.il* e produce l'eseguibile *myTestFile.exe*.

```console
ilasm myTestFile
```

Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll**myTestFile.dll*.

```console
ilasm myTestFile /dll
```

Il comando che segue assembla il file IL *myTestFile.il* e produce il file *.dll**myNewTestFile.dll*.

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

L'esempio di codice seguente illustra un'applicazione molto semplice che visualizza "Hello World!" nella console. È possibile compilare questo codice e quindi utilizzare lo strumento [*Ildasm. exe*](ildasm-exe-il-disassembler.md) per generare un file il.

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

L'esempio di codice IL riportato di seguito corrisponde al precedente esempio di codice C#. È possibile compilare questo codice in un assembly mediante lo strumento IL Assembler. Gli esempi di codice IL e C# visualizzano entrambi "Hello World!" nella console.

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [*Ildasm. exe* (disassembler il)](ildasm-exe-il-disassembler.md)
- [Processo di esecuzione gestita](../../standard/managed-execution-process.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
