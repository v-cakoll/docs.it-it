---
title: 'Procedura dettagliata: creazione di oggetti COM con Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: caf0a071d65746f1027052e648ade538d62dc4bb
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245687"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Procedura dettagliata: creazione di oggetti COM con Visual Basic
Quando si creano nuove applicazioni o componenti, è consigliabile creare gli assembly di .NET Framework. Tuttavia, Visual Basic semplifica per esporre un componente di .NET Framework a COM. In questo modo è possibile fornire nuovi componenti per la suite di applicazioni precedenti che richiedono i componenti COM. Questa procedura dettagliata illustra come usare Visual Basic per esporre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] oggetti come oggetti COM, con e senza il modello di classe COM.  
  
 Per esporre gli oggetti COM in modo semplice consiste nell'usare il modello di classe COM. Il modello di classe COM consente di creare una nuova classe e quindi Configura il progetto per generare il livello di classe e l'interoperabilità come un oggetto COM e registrarla con il sistema operativo.  
  
> [!NOTE]
>  Sebbene sia possibile esporre anche una classe creata in Visual Basic come oggetto COM per codice non gestito da usare, non è un vero oggetto COM e non può essere utilizzato da Visual Basic. Per altre informazioni, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Per creare un oggetto COM usando il modello di classe COM  
  
1.  Aprire un nuovo progetto di applicazione di Windows dal **File** menu, fare clic su **nuovo progetto**.  
  
2.  Nel **nuovo progetto** nella finestra di dialogo il **tipi di progetto** campo, verificare che Windows sia selezionato. Selezionare **libreria di classi** dalle **modelli** elenco e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.  
  
3.  Selezionare **Aggiungi nuovo elemento** dalle **progetto** menu. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
4.  Selezionare **classe COM** dalle **modelli** elenco e quindi fare clic su **Add**. Visual Basic consente di aggiungere una nuova classe e configura il nuovo progetto per l'interoperabilità COM.  
  
5.  Aggiungere il codice, ad esempio proprietà, metodi ed eventi della classe COM.  
  
6.  Selezionare **Compila ClassLibrary1** dalle **compilazione** menu. Visual Basic compilato l'assembly e registra l'oggetto COM con il sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Creazione di oggetti COM senza il modello classe COM  
 È anche possibile creare una classe COM anziché manualmente usando il modello di classe COM. Questa procedura è utile quando si lavora dalla riga di comando o se si desidera maggiore controllo sul modo in cui sono definiti gli oggetti COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Per configurare il progetto per generare un oggetto COM  
  
1.  Aprire un nuovo progetto di applicazione di Windows dal **File** menu, fare clic su **NewProject**.  
  
2.  Nel **nuovo progetto** nella finestra di dialogo il **tipi di progetto** campo, verificare che Windows sia selezionato. Selezionare **libreria di classi** dalle **modelli** elenco e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.  
  
3.  Nelle **Esplora soluzioni**mouse sul progetto e quindi fare clic su **proprietà**. Il **Progettazione progetti** viene visualizzato.  
  
4.  Fare clic sulla scheda **Compila**.  
  
5.  Selezionare il **Registra per interoperabilità COM** casella di controllo.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Per configurare il codice nella classe per creare un oggetto COM  
  
1.  Nelle **Esplora soluzioni**, fare doppio clic su **Class1.vb** per visualizzare il relativo codice.  
  
2.  Rinominare la classe come `ComClass1`.  
  
3.  Aggiungere le costanti seguenti al `ComClass1`. Si archivierà le costanti di identificatore univoco globale (GUID) che sono necessari affinché gli oggetti COM.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  Scegliere **Crea GUID** dal menu **Strumenti**. Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**. Fare clic su **Esci**.  
  
5.  Sostituire la stringa vuota per il `ClassId` con il GUID, rimuovendo le iniziali e finali dalle parentesi graffe. Ad esempio, se il GUID fornito da Guidgen è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` quindi il codice deve apparire come segue.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Ripetere i passaggi precedenti per il `InterfaceId` e `EventsId` costanti, come nell'esempio seguente.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Assicurarsi che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbero essere in conflitto con altri componenti COM.  
  
7.  Aggiungere il `ComClass` dell'attributo `ComClass1`, che specifica il GUID per l'ID della classe, l'ID di interfaccia e gli ID di eventi come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Classi COM devono avere un costruttore `Public Sub New()` costruttore o classe non registrerà correttamente. Aggiungere un costruttore senza parametri alla classe:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Aggiungere le proprietà, metodi ed eventi alla classe, che termina con un `End Class` istruzione. Selezionare **Compila soluzione** dalle **compilazione** menu. Visual Basic compilato l'assembly e registra l'oggetto COM con il sistema operativo.  
  
    > [!NOTE]
    >  Gli oggetti COM che è generare con Visual Basic non possono essere utilizzati da altre applicazioni Visual Basic perché non sono oggetti COM true. I tentativi di aggiungere i riferimenti a tali oggetti COM genererà un errore. Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)  
 [Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
