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
ms.openlocfilehash: 2e2cbac6fad5e1686b7383c44619b8c6f5326483
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396804"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Procedura: fare riferimento a oggetti COM da Visual Basic
In Visual Basic l'aggiunta di riferimenti a oggetti COM con librerie dei tipi richiede la creazione di un assembly di interoperabilità per la libreria COM. I riferimenti ai membri dell'oggetto COM vengono instradati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo. Le risposte dall'oggetto COM vengono instradate all'assembly di interoperabilità e inoltrate all'applicazione .NET Framework.  
  
 È possibile fare riferimento a un oggetto COM senza utilizzare un assembly di interoperabilità incorporando le informazioni sul tipo per l'oggetto COM in un assembly .NET. Per incorporare le informazioni sul tipo, impostare la `Embed Interop Types` proprietà su `True` per il riferimento all'oggetto com. Se si esegue la compilazione utilizzando il compilatore da riga di comando, utilizzare l' `/link` opzione per fare riferimento alla libreria com. Per ulteriori informazioni, vedere [-link (Visual Basic)](../../reference/command-line-compiler/link.md).  
  
 Visual Basic crea automaticamente assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'Integrated Development Environment (IDE). Quando si utilizza la riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente assembly di interoperabilità.  
  
### <a name="to-add-references-to-com-objects"></a>Per aggiungere riferimenti a oggetti COM  
  
1. Scegliere **Aggiungi riferimento** dal menu **progetto** , quindi fare clic sulla scheda **com** nella finestra di dialogo.  
  
2. Consente di selezionare il componente che si desidera utilizzare dall'elenco di oggetti COM.  
  
3. Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un' `Imports` istruzione all'inizio della classe o del modulo in cui si utilizzerà l'oggetto com. Ad esempio, nell'esempio di codice seguente viene importato lo spazio dei nomi `INKEDLib` per gli oggetti a cui si fa riferimento nella `Microsoft InkEdit Control 1.0` libreria.  
  
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

- [Interoperabilità COM](index.md)
- [Tlbimp. exe (utilità di importazione della libreria di tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp. exe (utilità di esportazione della libreria di tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [Risoluzione dei problemi relativi all'interoperabilità](troubleshooting-interoperability.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
