---
title: Attributi comuni
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400719"
---
# <a name="common-attributes-visual-basic"></a>Attributi comuni (Visual Basic)

In questo argomento vengono descritti gli attributi usati più di frequente nei programmi Visual Basic.

- [Attributi globali](#Global)

- [Attributo obsolete](#Obsolete)

- [Attributo condizionale](#Conditional)

- [Attributi delle informazioni sul chiamante](#CallerInfo)

- [Attributi di Visual Basic](#VB)

## <a name="global-attributes"></a><a name="Global"></a>Attributi globali

La maggior parte degli attributi viene applicata a elementi specifici del linguaggio quali classi o metodi. Alcuni attributi sono invece globali e vengono applicati a un intero assembly o a un intero modulo. Ad esempio, l'attributo <xref:System.Reflection.AssemblyVersionAttribute> può essere usato per incorporare informazioni sulla versione in un assembly, nel modo seguente:

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

Gli attributi globali vengono visualizzati nel codice sorgente dopo qualsiasi istruzione di primo livello `Imports` e prima delle dichiarazioni di tipo, modulo o spazio dei nomi. Gli attributi globali possono apparire in più file di origine, ma i file devono essere compilati in un'unica operazione di compilazione. Per i progetti Visual Basic, gli attributi globali vengono in genere inseriti nel file AssemblyInfo. vb. il file viene creato automaticamente quando si crea un progetto in Visual Studio.

Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly. Sono suddivisi nelle seguenti categorie:

- Attributi relativi all'identità dell'assembly

- Attributi informativi

- Attributi relativi al manifesto dell'assembly

### <a name="assembly-identity-attributes"></a>Attributi relativi all'identità dell'assembly

Tre attributi (con un nome sicuro, se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura. Questi attributi formano il nome completo dell'assembly e sono necessari per creare riferimenti all'assembly nel codice. È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly. Tuttavia il valore del nome viene impostato alla creazione dell'assembly dal compilatore (l'IDE di Visual Studio nella [finestra di dialogo informazioni Assembly](/visualstudio/ide/reference/assembly-information-dialog-box) oppure Assembly Linker, Al.exe), in base al file che contiene il manifesto dell'assembly. L'attributo <xref:System.Reflection.AssemblyFlagsAttribute> specifica se è supportata la coesistenza di più copie dell'assembly.

La tabella seguente visualizza gli attributi relativi all'identità.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|Descrive in modo completo l'identità di un assembly.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Specifica la versione di un assembly.|
|<xref:System.Reflection.AssemblyCultureAttribute>|Specifica le impostazioni cultura supportate dall'assembly.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Specifica se un assembly supporta l'esecuzione side-by-side nello stesso computer, nello stesso processo o nello stesso dominio dell'applicazione.|

### <a name="informational-attributes"></a>Attributi informativi

Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly. La tabella seguente mostra gli attributi informativi definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Definisce un attributo personalizzato che specifica un nome prodotto per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Definisce un attributo personalizzato che specifica un marchio registrato per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Definisce un attributo personalizzato che specifica una versione informativa per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Definisce un attributo personalizzato che specifica un nome società per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Definisce un attributo personalizzato che specifica un copyright per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Indica al compilatore di usare un numero di versione specifico per la risorsa della versione del file Win32.|
|<xref:System.CLSCompliantAttribute>|Indica se l'assembly è conforme a CLS (Common Language Specification).|

### <a name="assembly-manifest-attributes"></a>Attributi relativi al manifesto dell'assembly

È possibile usare gli attributi relativi al manifesto dell'assembly per includere informazioni nel manifesto dell'assembly. Queste informazioni includono il titolo, la descrizione, l'alias predefinito e la configurazione. La tabella seguente visualizza gli attributi del manifesto dell'assembly definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Definisce un attributo personalizzato che specifica un titolo assembly per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Definisce un attributo personalizzato che specifica una descrizione assembly per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Definisce un attributo personalizzato che specifica una configurazione assembly per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definisce un alias predefinito descrittivo per un manifesto dell'assembly.|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a>Attributo obsolete

L'attributo `Obsolete` contrassegna un'entità del programma il cui uso non è più consigliato. Ogni uso di un'entità contrassegnata con Obsolete genererà in seguito un avviso o errore, a seconda della configurazione dell'attributo. Ad esempio:

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

Nel seguente esempio l'attributo `Obsolete` viene applicato alla classe `A` e al metodo `B.OldMethod`. Poiché il secondo argomento del costruttore dell'attributo applicato a `B.OldMethod` è impostato su `true` questo metodo genererà un errore del compilatore, mentre l'uso della classe `A` produrrà semplicemente un avviso. Tuttavia la chiamata di `B.NewMethod` non produrrà né un avviso né un errore.

La stringa specificata come primo argomento al costruttore dell'attributo viene inclusa nell'avviso o nell'errore visualizzato. Ad esempio, se viene usato con le definizioni precedenti, il codice che segue genera due avvisi e un errore:

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

Vengono generati due avvisi per la classe `A`: uno per la dichiarazione del riferimento alla classe e uno per il costruttore della classe.

L'attributo `Obsolete` può essere usato senza argomenti, ma è consigliabile includere la spiegazione del motivo per cui l'elemento è obsoleto e l'indicazione degli elementi di codice da usare come alternativa.

`Obsolete` è un attributo monouso e può essere applicato a qualsiasi entità che supporta gli attributi. `Obsolete` è un alias per <xref:System.ObsoleteAttribute>.

## <a name="conditional-attribute"></a><a name="Conditional"></a> Attributo Conditional

L'attributo `Conditional` rende l'esecuzione di un metodo dipendente da un identificatore di pre-elaborazione. L'attributo `Conditional` è un alias per <xref:System.Diagnostics.ConditionalAttribute> e può essere applicato a un metodo o a una classe Attribute.

In questo esempio, `Conditional` viene applicato a un metodo per attivare o disattivare la visualizzazione di informazioni di diagnostica specifiche del programma:

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

Se l'identificatore `TRACE_ON` non è definito, non viene visualizzato nessun output di traccia.

L'attributo `Conditional` viene usato spesso con l'identificatore `DEBUG` per abilitare funzioni di traccia e registrazione nelle compilazioni di debug ma non nelle build di rilascio, come segue:

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

Quando viene chiamato un metodo contrassegnato come condizionale, la presenza o l'assenza del simbolo di pre-elaborazione specificato determina se la chiamata viene inclusa o omessa. Se il simbolo è definito la chiamata viene inclusa, in caso contrario viene omessa. L'uso di `Conditional` rappresenta un'alternativa più efficiente, elegante e meno soggetta a errori rispetto all'inclusione di metodi nei blocchi `#if…#endif` come segue:

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

Un metodo condizionale deve essere un metodo in una dichiarazione di classe o struct e non deve avere un valore restituito.

### <a name="using-multiple-identifiers"></a>Usare più identificatori

Se un metodo ha più attributi `Conditional`, una chiamata al metodo è inclusa se è definito almeno uno dei simboli condizionali (in altre parole, se i simboli sono collegati tra loro a livello logico mediante l'operatore OR). In questo esempio la presenza di `A` o `B` determina una chiamata al metodo:

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

Per ottenere il collegamento logico di simboli tramite l'operatore AND è possibile definire metodi condizionali seriali. Ad esempio, il secondo metodo riportato di seguito viene eseguito solo se sono definiti sia `A` sia `B`:

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a>Usare Conditional con le classi di attributi

L'attributo `Conditional` può essere applicato anche a una definizione di classe Attribute. In questo esempio l'attributo personalizzato `Documentation` aggiunge le informazioni ai metadati solo se è definito l'elemento DEBUG.

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a>Attributi delle informazioni sul chiamante

Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo. È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.

È possibile ottenere informazioni sul chiamante usando gli attributi applicati ai parametri facoltativi. Ogni parametro facoltativo specifica un valore predefinito. Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:

|Attributo|Descrizione|Type|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Percorso completo del file di origine contenente il chiamante. È il percorso al momento della compilazione.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Numero di riga nel file di origine da cui viene chiamato il metodo.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nome di una proprietà o di un metodo del chiamante. Per ulteriori informazioni, vedere [informazioni sul chiamante (Visual Basic)](../caller-information.md).|`String`|

Per ulteriori informazioni sugli attributi delle informazioni sul chiamante, vedere [informazioni sul chiamante (Visual Basic)](../caller-information.md).

## <a name="visual-basic-attributes"></a><a name="VB"></a>Attributi di Visual Basic

Nella tabella seguente sono elencati gli attributi specifici per Visual Basic.

|Attributo|Scopo|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|Indica al compilatore che la classe deve essere esposta come oggetto COM.|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Consente l'accesso ai membri del modulo usando solo la qualifica necessaria per il modulo.|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Specifica la dimensione di una stringa a lunghezza fissa in una struttura da utilizzare con le funzioni di input e output di file.|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Specifica la dimensione di una matrice fissa in una struttura da utilizzare con le funzioni di input e output di file.|

### <a name="comclassattribute"></a>COMClassAttribute

Usare `COMClassAttribute` per semplificare il processo di creazione di componenti com da Visual Basic. Gli oggetti COM sono molto diversi dagli assembly .NET Framework e senza `COMClassAttribute` , è necessario seguire una serie di passaggi per generare un oggetto com da Visual Basic. Per le classi contrassegnate con `COMClassAttribute` , il compilatore esegue automaticamente molti di questi passaggi.

### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute

Usare `HideModuleNameAttribute` per consentire l'accesso ai membri del modulo usando solo la qualifica necessaria per il modulo.

### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute

Usare `VBFixedStringAttribute` per forzare Visual Basic a creare una stringa a lunghezza fissa. Per impostazione predefinita, le stringhe sono di lunghezza variabile e questo attributo è utile quando si archiviano le stringhe nei file. Il codice seguente illustra questo processo:

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute

Utilizzare `VBFixedArrayAttribute` per dichiarare matrici di dimensioni fisse. Come Visual Basic stringhe, le matrici hanno una lunghezza variabile per impostazione predefinita. Questo attributo è utile per la serializzazione o la scrittura di dati in file.

## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guida per programmatori Visual Basic](../../index.md)
- [Attributi](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../reflection.md)
- [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)
