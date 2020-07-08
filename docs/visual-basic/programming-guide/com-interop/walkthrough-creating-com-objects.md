---
title: 'Procedura dettagliata: Creazione di oggetti COM'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 6ff23f73af384a1440bcebd4b6bac21714e01756
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051480"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Procedura dettagliata: creazione di oggetti COM con Visual Basic
Quando si creano nuovi componenti o applicazioni, è consigliabile creare .NET Framework assembly. Tuttavia, Visual Basic facilita anche l'esposizione di un componente .NET Framework a COM. In questo modo è possibile fornire nuovi componenti per i gruppi di applicazioni precedenti che richiedono componenti COM. In questa procedura dettagliata viene illustrato come utilizzare Visual Basic per esporre .NET Framework oggetti come oggetti COM, sia con sia senza il modello di classe COM.  
  
 Il modo più semplice per esporre oggetti COM consiste nell'usare il modello di classe COM. Questo modello crea una nuova classe, quindi configura il progetto per generare la classe con un livello di interoperabilità come oggetto COM e la registra con il sistema operativo.  
  
> [!NOTE]
> Sebbene sia anche possibile esporre una classe creata in Visual Basic come oggetto COM per il codice non gestito da usare, non è un vero oggetto COM e non può essere usata da Visual Basic. Per ulteriori informazioni, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Per creare un oggetto COM utilizzando il modello di classe COM  
  
1. Aprire un nuovo progetto di applicazione Windows dal menu **file** facendo clic su **nuovo progetto**.  
  
2. Nella finestra di dialogo **nuovo progetto** , sotto il campo **Tipi progetto** , verificare che sia selezionata l'opzione Windows. Selezionare **libreria di classi** dall'elenco **modelli** , quindi fare clic su **OK**. Verrà visualizzato il nuovo progetto.  
  
3. Scegliere **Aggiungi nuovo elemento** dal menu **progetto** . La finestra di dialogo **Aggiungi nuovo elemento** viene visualizzata.  
  
4. Selezionare **classe com** dall'elenco **modelli** , quindi fare clic su **Aggiungi**. Visual Basic aggiunge una nuova classe e configura il nuovo progetto per l'interoperabilità COM.  
  
5. Aggiungere codice come proprietà, metodi ed eventi alla classe COM.  
  
6. Scegliere **Compila ClassLibrary1** dal menu **Compila** . Visual Basic compila l'assembly e registra l'oggetto COM con il sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Creazione di oggetti COM senza il modello di classe COM  
 È inoltre possibile creare manualmente una classe COM anziché utilizzare il modello di classe COM. Questa procedura è utile quando si utilizza la riga di comando o quando si desidera un maggiore controllo sulla modalità di definizione degli oggetti COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Per configurare il progetto per generare un oggetto COM  
  
1. Aprire un nuovo progetto di applicazione Windows dal menu **file** facendo clic su **NewProject**.  
  
2. Nella finestra di dialogo **nuovo progetto** , sotto il campo **Tipi progetto** , verificare che sia selezionata l'opzione Windows. Selezionare **libreria di classi** dall'elenco **modelli** , quindi fare clic su **OK**. Verrà visualizzato il nuovo progetto.  
  
3. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**. Verrà visualizzato **Progettazione progetti** .  
  
4. Fare clic sulla scheda **Compila**.  
  
5. Selezionare la casella **di controllo registra per interoperabilità COM** .  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Per configurare il codice nella classe per creare un oggetto COM  
  
1. In **Esplora soluzioni**fare doppio clic su **Class1. vb** per visualizzarne il codice.  
  
2. Rinominare la classe in `ComClass1`.  
  
3. Aggiungere le costanti seguenti a `ComClass1` . Verranno archiviate le costanti identificatore univoco globale (GUID) che devono essere presenti negli oggetti COM.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. Scegliere **Crea GUID** dal menu **Strumenti**. Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**. Fare clic su **Esci**.  
  
5. Sostituire la stringa vuota per `ClassId` con il GUID, rimuovendo le parentesi graffe iniziali e finali. Se, ad esempio, il GUID fornito da GUIDGEN è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , il codice dovrebbe essere simile al seguente.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Ripetere i passaggi precedenti per le `InterfaceId` `EventsId` costanti e, come nell'esempio seguente.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > Verificare che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbe essere in conflitto con altri componenti COM.  
  
7. Aggiungere l' `ComClass` attributo a `ComClass1` , specificando i GUID per l'ID di classe, l'ID di interfaccia e l'ID degli eventi come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. Le classi COM devono avere un `Public Sub New()` costruttore senza parametri o la classe non sarà registrata correttamente. Aggiungere un costruttore senza parametri alla classe:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Aggiungere proprietà, metodi ed eventi alla classe, terminando con un' `End Class` istruzione. Scegliere **Compila soluzione** dal menu **Compila** . Visual Basic compila l'assembly e registra l'oggetto COM con il sistema operativo.  
  
    > [!NOTE]
    > Gli oggetti COM generati con Visual Basic non possono essere utilizzati da altre applicazioni Visual Basic perché non sono veri oggetti COM. I tentativi di aggiungere riferimenti a tali oggetti COM genereranno un errore. Per informazioni dettagliate, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [Interoperabilità COM](index.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [#Region (direttiva)](../../language-reference/directives/region-directive.md)
- [Interoperabilità COM nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md)
- [Risoluzione dei problemi relativi all'interoperabilità](troubleshooting-interoperability.md)
