---
title: Esempio di tecnologia di serializzazione di base
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: dc190a93e45bf2b682aff0158ccd42bc09762d9a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315010"
---
# <a name="basic-serialization-technology-sample"></a>Esempio di tecnologia di serializzazione di base
[Scarica esempio](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)  
  
 In questo esempio viene illustrata la capacità di Common Language Runtime di serializzare in un flusso il grafico di un oggetto contenuto in memoria. Per la serializzazione, è possibile utilizzare l'oggetto <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Un elenco collegato, contenente dati, viene serializzato in un flusso di file o deserializzato da tale flusso. In entrambi i casi l'elenco viene visualizzato per consentire di esaminare i risultati. L'elenco collegato è di tipo `LinkedList`, un tipo definito in questo esempio.  
  
 Per ulteriori informazioni sulla serializzazione, vedere i commenti nei file di codice sorgente e build.proj.  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a>Per compilare l'esempio utilizzando il prompt dei comandi  
  
1. Spostarsi in una delle sottodirectory specifiche del linguaggio della directory Technologies\Serialization\Runtime Serialization\Basic utilizzando il prompt dei comandi.  
  
2. Dalla riga di comando digitare **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, a seconda del linguaggio di programmazione che si vuole usare.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Per compilare l'esempio utilizzando Visual Studio  
  
1. Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.  
  
2. Fare doppio clic sull'icona relativa a SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, a seconda del linguaggio di programmazione che si desidera utilizzare, per aprire il file in Visual Studio.  
  
3. Scegliere **Compila soluzione** dal menu **Compila**.  
  
 L'applicazione verrà compilata nella sottodirectory predefinita \bin o \bin\Debug.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1. Spostarsi nella directory contenente l'eseguibile compilato.  
  
2. Dalla riga di comando digitare **Serialization.exe** con i valori di parametro desiderati.  
  
    > [!NOTE]
    >  L'esempio compila un'applicazione console. Per visualizzare l'output dell'applicazione, è necessario avviarla dalla finestra del prompt dei comandi.  
  
## <a name="remarks"></a>Note  
 L'applicazione di esempio accetta parametri della riga di comando che indicano il test da eseguire. Per serializzare un elenco costituito da 10 nodi in un file denominato **Test.xml** tramite il formattatore SOAP, usare i parametri **sx Test.xml 10**.  
  
 Di seguito è riportato un esempio:  
  
 **Serialize.exe -sx Test.xml 10**  
  
 Per deserializzare il file **Test.xml** dell'esempio precedente, usare i parametri **dx Test.xml**.  
  
 Di seguito è riportato un esempio:  
  
 **Serialize.exe -dx Test.xml**  
  
 Nei due esempi precedenti, la lettera "x" nell'opzione della riga di comando indica che si desidera utilizzare la serializzazione SOAP XML. Per utilizzare la serializzazione binaria, è possibile utilizzare la lettera "b". Se si desidera eseguire la serializzazione con un numero di nodi molto elevato, può essere opportuno reindirizzare l'output della console in un file.  
  
 Di seguito è riportato un esempio:  
  
 **Serialize.exe -sb Test.bin 10000 >somefile.txt**  
  
 Nell'elenco riportato di seguito vengono descritte in modo sintetico le classi e le tecnologie utilizzate nell'esempio.  
  
-   Serializzazione in fase di esecuzione  
  
    -   <xref:System.Runtime.Serialization.IFormatter> Utilizzato per fare riferimento a un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o un <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> oggetto.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Utilizzato per serializzare un elenco collegato a un flusso in un formato binario. Il formattatore binario utilizza un formato riconosciuto solo dal tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Tuttavia, i dati sono concisi.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Utilizzato per serializzare un elenco collegato a un flusso in formato SOAP. che è un formato standard.  
  
-   I/O di flusso  
  
    -   <xref:System.IO.Stream> Utilizzato per serializzare e deserializzare. Il tipo di flusso specifico utilizzato in questo esempio è <xref:System.IO.FileStream>. È tuttavia possibile utilizzare la serializzazione con qualsiasi tipo derivato da <xref:System.IO.Stream>.  
  
    -   <xref:System.IO.File> Consente di creare <xref:System.IO.FileStream> oggetti per la lettura e la creazione di file su disco.  
  
    -   <xref:System.IO.FileStream> Utilizzato per serializzare e deserializzare gli elenchi collegati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [Serializzazione di base](../../../docs/standard/serialization/basic-serialization.md)
- [Serializzazione binaria](../../../docs/standard/serialization/binary-serialization.md)
- [Controllo della serializzazione XML mediante attributi](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Serializzazione](../../../docs/standard/serialization/index.md)
- [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)
