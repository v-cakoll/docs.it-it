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
ms.openlocfilehash: 34f46a1ea9c728cbaeb0456f8a6751ff529f2903
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43801690"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Procedura: fare riferimento a oggetti COM da Visual Basic
In Visual Basic, l'aggiunta di riferimenti a oggetti COM con librerie dei tipi richiede la creazione di un assembly di interoperabilità per la libreria COM. I riferimenti ai membri dell'oggetto COM vengono indirizzati all'assembly di interoperabilità e quindi inoltrati all'oggetto COM effettivo. Le risposte dall'oggetto COM vengono indirizzate all'assembly di interoperabilità e inoltrate al [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione.  
  
 È possibile fare riferimento a un oggetto COM senza usare un assembly di interoperabilità per incorporare le informazioni sul tipo per l'oggetto COM in un assembly .NET. Per incorporare le informazioni sul tipo, impostare il `Embed Interop Types` proprietà `True` per il riferimento all'oggetto COM. Se esegue la compilazione usando il compilatore della riga di comando, usare il `/link` opzione per fare riferimento alla libreria COM. Per altre informazioni, vedere [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic crea automaticamente gli assembly di interoperabilità quando si aggiunge un riferimento a una libreria dei tipi dall'ambiente di sviluppo integrato (IDE). Quando si lavora dalla riga di comando, è possibile utilizzare l'utilità Tlbimp per creare manualmente gli assembly di interoperabilità.  
  
### <a name="to-add-references-to-com-objects"></a>Per aggiungere riferimenti agli oggetti COM  
  
1.  Nel **progetto** menu, scegliere **Aggiungi riferimento** e quindi fare clic sui **COM** scheda nella finestra di dialogo.  
  
2.  Selezionare il componente da usare dall'elenco di oggetti COM.  
  
3.  Per semplificare l'accesso all'assembly di interoperabilità, aggiungere un `Imports` istruzione all'inizio della classe o modulo in cui si userà l'oggetto COM. Ad esempio, il codice seguente importa lo spazio dei nomi `INKEDLib` per gli oggetti a cui fa riferimento il `Microsoft InkEdit Control 1.0` libreria.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Per creare un assembly di interoperabilità tramite Tlbimp  
  
1.  Aggiungere il percorso di Tlbimp al percorso di ricerca, se non è già parte del percorso di ricerca e non si è attualmente nella directory in cui si trova.  
  
2.  Tlbimp chiamata da un prompt dei comandi, fornendo le informazioni seguenti:  
  
    -   Nome e il percorso della DLL che contiene la libreria dei tipi  
  
    -   Nome e il percorso dello spazio dei nomi in cui devono essere inserite le informazioni  
  
    -   Nome e percorso dell'assembly di interoperabilità.  
  
     Nel codice seguente ne viene illustrato un esempio:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     È possibile utilizzare Tlbimp per creare assembly di interoperabilità di librerie dei tipi, anche per gli oggetti COM non registrati. Tuttavia, gli oggetti COM a cui fa riferimento l'assembly di interoperabilità devono essere registrati correttamente nel computer in cui sono utilizzabili. È possibile registrare un oggetto COM tramite l'utilità Regsvr32 incluso con il sistema operativo Windows.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](https://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
