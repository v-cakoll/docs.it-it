---
title: 'Procedura: fare riferimento a oggetti COM da Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: ea0e1d9b0ae9f151d901c425512508ba7bc05343
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524364"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Procedura: fare riferimento a oggetti COM da Visual Basic
In Visual Basic l'aggiunta di riferimenti a oggetti COM con librerie dei tipi richiede la creazione di un assembly di interoperabilità per la libreria COM. I riferimenti ai membri dell'oggetto COM vengono instradati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo. Le risposte dall'oggetto COM vengono instradate all'assembly di interoperabilità e inoltrate all'applicazione .NET Framework.  
  
 È possibile fare riferimento a un oggetto COM senza utilizzare un assembly di interoperabilità incorporando le informazioni sul tipo per l'oggetto COM in un assembly .NET. Per incorporare le informazioni sul tipo, impostare la proprietà `Embed Interop Types` su `True` per il riferimento all'oggetto COM. Se si esegue la compilazione utilizzando il compilatore da riga di comando, utilizzare l'opzione `/link` per fare riferimento alla libreria COM. Per ulteriori informazioni, vedere [-link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic crea automaticamente assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'Integrated Development Environment (IDE). Quando si utilizza la riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente assembly di interoperabilità.  
  
### <a name="to-add-references-to-com-objects"></a>Per aggiungere riferimenti a oggetti COM  
  
1. Scegliere **Aggiungi riferimento** dal menu **progetto** , quindi fare clic sulla scheda **com** nella finestra di dialogo.  
  
2. Consente di selezionare il componente che si desidera utilizzare dall'elenco di oggetti COM.  
  
3. Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un'istruzione `Imports` all'inizio della classe o del modulo in cui si utilizzerà l'oggetto COM. Nell'esempio di codice seguente, ad esempio, viene importato lo spazio dei nomi `INKEDLib` per gli oggetti a cui si fa riferimento nella libreria `Microsoft InkEdit Control 1.0`.  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Per creare un assembly di interoperabilità tramite Tlbimp  
  
1. Aggiungere il percorso di Tlbimp al percorso di ricerca, se non è già incluso nel percorso di ricerca e non si è attualmente nella directory in cui si trova.  
  
2. Chiamare Tlbimp da un prompt dei comandi, fornendo le informazioni seguenti:  
  
    - Nome e percorso della DLL contenente la libreria dei tipi  
  
    - Nome e percorso dello spazio dei nomi in cui devono essere inserite le informazioni  
  
    - Nome e percorso dell'assembly di interoperabilità di destinazione  
  
     Nel codice seguente ne viene illustrato un esempio:  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     È possibile utilizzare Tlbimp per creare assembly di interoperabilità per le librerie dei tipi, anche per gli oggetti COM non registrati. Tuttavia, gli oggetti COM a cui fanno riferimento gli assembly di interoperabilità devono essere registrati correttamente nel computer in cui devono essere utilizzati. È possibile registrare un oggetto COM utilizzando l'utilità Regsvr32 inclusa nel sistema operativo Windows.  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
