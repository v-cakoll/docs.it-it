---
title: Mgmtclassgen.exe (Management Strongly Typed Class Generator)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: 5e39670fbb40acb999a243ac86683219f3c89e4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180375"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a>Mgmtclassgen.exe (Management Strongly Typed Class Generator)
Lo strumento Generatore di classi di gestione fortemente tipizzate consente di generare velocemente una classe gestita ad associazione precoce per una specifica classe WMI (Windows Management Instrumentation, Strumentazione gestita Windows). L'utilizzo della classe generata semplifica la scrittura del codice per l'accesso a un'istanza della classe WMI.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|*classeWMI*|Classe WMI per la quale generare una classe gestita ad associazione precoce.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/l**  *linguaggio*|Specifica il linguaggio in cui generare la classe gestita ad associazione precoce. È possibile specificare **CS** (C#; impostazione predefinita), **VB** (Visual Basic),  **MC** (C++) o  **JS** (JScript) come argomento del linguaggio.|  
|**/m**  *computer*|Specifica il computer al quale eseguire la connessione ovvero quello sul quale risiede la classe WMI. Il valore predefinito è il computer locale.|  
|**/n**  *percorso*|Specifica il percorso dello spazio dei nomi WMI contenente la classe WMI. Se non si specifica questa opzione, lo strumento genera codice per *classeWMI* nello spazio dei nomi **Root\cimv2** predefinito.|  
|**/o**  *spazionomiclasse*|Specifica lo spazio dei nomi .NET nel quale generare la classe di codice gestito. Se non si specifica questa opzione, lo spazio dei nomi verrà generato utilizzando lo spazio dei nomi WMI e il prefisso dello schema. Il prefisso dello schema è la parte del nome della classe che precede il carattere di sottolineatura. Ad esempio, per la classe **Win32_OperatingSystem** nello spazio dei nomi **Root\cimv2**, lo strumento genera la classe in **ROOT.CIMV2.Win32**.|  
|**/p**  *percorsofile*|Specifica il percorso del file in cui salvare il codice generato. Se non si specifica questa opzione, il file verrà creato nella directory corrente. Denomina la classe e il file in cui viene generata la classe con l'argomento *classeWMI*. Il nome della classe e del file è uguale al nome di *classeWMI*. Se il nome di *classeWMI* include un carattere di sottolineatura, lo strumento usa la parte del nome della classe che segue tale carattere. Ad esempio, se il nome di *classeWMI* è nel formato **Win32_LogicalDisk**, il nome della classe e del file generati sarà "logicaldisk". Se esiste già un file con tale nome, verrà sovrascritto.|  
|**/pw**  *password*|Specifica la password da usare per l'accesso a un computer specificato dall'opzione **/m**.|  
|**/u**  *nomeutente*|Specifica il nome utente da usare per l'accesso a un computer specificato dall'opzione **/m**.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Osservazioni  
 Mgmtclassgen.exe utilizza il metodo <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>. È possibile pertanto utilizzare un provider di codice personalizzato per generare codice in linguaggi gestiti diversi da C#, Visual Basic e JScript.  
  
 Le classi generate sono associate allo schema per il quale sono state generate. Quando lo schema sottostante una classe viene modificato è necessario generare nuovamente la classe se si desidera che essa rispecchi le modifiche dello schema.  
  
 Nella tabella riportata di seguito viene illustrato il mapping tra i tipi CIM (Common Information Model) WMI e i tipi dati inclusi in una classe generata.  
  
|Tipo CIM|Tipo di dati incluso nella classe generata|  
|--------------|--------------------------------------|  
|CIM_SINT8|**Sbyte**|  
|CIM_UINT8|**Byte**|  
|CIM_SINT16|**Int16**|  
|CIM_UINT16|**UInt16**|  
|CIM_SINT32|**Int32**|  
|SIM_UINT32|**UInt32**|  
|CIM_SINT64|**Int64**|  
|CIM_UINT64|**UInt64**|  
|CIM_REAL32|**Singolo**|  
|CIM_REAL64|**Doppia**|  
|CIM_BOOLEAN|**Boolean**|  
|CIM_String|**Stringa**|  
|CIM_DATETIME|**DateTime** o **TimeSpan**|  
|CIM_REFERENCE|**ManagementPath**|  
|CIM_CHAR16|**Char**|  
|CIM_OBJECT|**ManagementBaseObject**|  
|CIM_IUNKNOWN|**Oggetto**|  
|CIM_ARRAY|Matrice degli oggetti precedenti|  
  
 Quando viene generata una classe WMI può accadere quanto segue:  
  
- Una proprietà o un metodo pubblico standard può avere lo stesso nome di una proprietà o di un metodo esistente. In tal caso il nome della proprietà o del metodo nella classe generata verrà automaticamente cambiato per evitare conflitti di denominazione.  
  
- Il nome di una proprietà o di un metodo in una classe generata può essere una parola chiave nel linguaggio di programmazione di destinazione. In tal caso il nome della proprietà o del metodo nella classe generata verrà automaticamente cambiato per evitare conflitti di denominazione.  
  
- In WMI un qualificatore è un modificatore contenente informazioni per descrivere una classe, un'istanza, una proprietà o un metodo. Per descrivere una proprietà in una classe generata, WMI usa qualificatori standard quali **Read**, **Write** e **Key**. Ad esempio, una proprietà modificata con il qualificatore **Read** viene definita solo con una funzione di accesso **get** della proprietà nella classe generata. Poiché una proprietà contrassegnata dal qualificatore **Read** è di sola lettura, non viene definita alcuna funzione di accesso **set**.  
  
- Una proprietà numerica può essere modificata tramite i qualificatori **Values** e **ValueMaps** per indicare che la proprietà può essere impostata solo su specifici valori consentiti. Viene generata un'enumerazione con i qualificatori **Values** e **ValueMaps** e viene eseguito il mapping della proprietà all'enumerazione.  
  
- La strumentazione WMI utilizza il termine Singleton per descrivere una classe che può avere una sola istanza. Il costruttore senza parametri per una classe singleton, pertanto, inizializzerà la classe per l'unica istanza della classe.  
  
- Le proprietà di una classe WMI possono essere oggetti. Quando si genera una classe fortemente tipizzata per questo tipo di classe WMI, valutare di generare classi fortemente tipizzate per i tipi delle proprietà oggetti incorporati. Sarà così possibile eseguire un accesso fortemente tipizzato agli oggetti incorporati. Il codice generato potrebbe non essere in grado di individuare il tipo dell'oggetto incorporato. In tal caso nel codice generato verrà creato un commento che notifica il problema. Sarà quindi possibile modificare il codice generato per tipizzare la proprietà sull'altra classe generata.  
  
- In WMI il valore dei dati del tipo di dati CIM_DATETIME può rappresentare una specifica data e ora o un intervallo di tempo. Se il valore dei dati rappresenta una data e un'ora, il tipo di dati nella classe generata è **DateTime**. Se il valore dei dati rappresenta un intervallo di tempo, il tipo di dati nella classe generata è **TimeSpan**.  
  
 In alternativa è possibile generare una classe fortemente tipizzata utilizzando l'estensione di gestione per Esplora server di Visual Studio .NET.  
  
 Per altre informazioni su WMI, vedere l'argomento **Windows Management Instrumentation** (Strumentazione gestione Windows (WMI)) nella documentazione di Platform SDK.  
  
## <a name="examples"></a>Esempi  
 Il comando seguente genera una classe gestita in codice C# per la classe WMI **Win32_LogicalDisk** nello spazio dei nomi **Root\cimv2**. Lo strumento scrive la classe gestita nel file di origine che si trova nel percorso c:\disk.cs dello spazio dei nomi **ROOT.CIMV2.Win32**.  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 Nel codice di esempio riportato di seguito viene illustrato come utilizzare una classe generata a livello di programmazione. Innanzitutto viene enumerata un'istanza della classe e viene visualizzato il percorso. In seguito, un'istanza della classe generata da inizializzare viene creata con un'istanza di WMI. `Process` è la classe generata per **Win32_Process** e `LogicalDisk` è la classe generata per **Win32_LogicalDisk** nello spazio dei nomi **Root\cimv2**.  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App
   Public Shared Sub Main()
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [Strumenti](index.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
