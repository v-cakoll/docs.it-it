---
title: 'Procedura: Ereditare form mediante la finestra di dialogo Selezione ereditarietà'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], forms
- Inheritance Picker dialog box
- inherited forms [Windows Forms], creating
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
ms.openlocfilehash: 9382f1bf890fb5a886cf547d9b1e9b3031c12eb6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039998"
---
# <a name="how-to-inherit-forms-using-the-inheritance-picker"></a>Procedura: Ereditare i form utilizzando la selezione ereditarietà

Il modo più semplice di ereditare un modulo o un altro oggetto consiste nell'usare la finestra di dialogo **Selezione ereditarietà**. In questo modo è possibile recuperare e riutilizzare il codice o un'interfaccia utente precedentemente creata in altre soluzioni.

> [!NOTE]
> Per ereditare da un modulo con la finestra di dialogo **Selezione ereditarietà**, il progetto che contiene il form deve essere incorporato in un file eseguibile o in una DLL. Per compilare il progetto scegliere **Compila soluzione** dal menu **Compila**.

## <a name="create-a-windows-form-by-using-the-inheritance-picker"></a>Creare un Windows Form usando la selezione ereditarietà

1. In Visual Studio scegliere **Aggiungi Windows Form**dal menu **progetto** .

   Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.

2. Cercare il modello di **modulo ereditato** da SearchBox o facendo clic sulla categoria **Windows Forms** , selezionarlo e denominarlo nella casella **nome** . Fare clic sul pulsante **Aggiungi** per procedere.

   Viene aperta la finestra di dialogo **Selezione ereditarietà**. Se il progetto corrente include già form, verranno visualizzati nella finestra di dialogo **Selezione ereditarietà**.

3. Per ereditare da un modulo in un altro assembly, fare clic sul pulsante **Sfoglia**.

4. Nella finestra di dialogo **Selezionare un file che contiene un componente da cui ereditare** passare al progetto contenente il form o il modulo desiderato.

5. Fare clic sul nome del file EXE o del file DLL per selezionarlo, quindi fare clic sul pulsante **Apri**.

   Verrà nuovamente visualizzata finestra di dialogo **Selezione ereditarietà**, in cui ora il componente risulta visualizzato unitamente al progetto in cui si trova.

6. Selezionare il componente.

   Il componente verrà aggiunto al progetto in **Esplora soluzioni**. Se dispone di un'interfaccia utente, i controlli che fanno parte del form ereditato verranno contrassegnati con un glifo (![screenshot del](./media/how-to-inherit-forms-using-the-inheritance-picker-dialog-box/visual-basic-inheritance-glyph.gif)simbolo di ereditarietà Visual Basic) e, se selezionati, avranno un bordo che indica il livello di sicurezza del controllo form con superclasse. I comportamenti che corrispondono ai vari livelli di sicurezza sono elencati nella tabella seguente.

    |Livello di sicurezza del controllo|Interazione possibile nella finestra di progettazione e nell'editor di codice con il form ereditato|
    |-------------------------------|--------------------------------------------------------------------------------|
    |Public|Bordo standard con quadratini di ridimensionamento: il controllo può essere ridimensionato e spostato. È possibile accedere al controllo internamente tramite la classe che lo dichiara ed esternamente tramite le altre classi.|
    |Protetta|Bordo standard con quadratini di ridimensionamento: il controllo può essere ridimensionato e spostato. È possibile accedere al controllo internamente tramite la classe che lo dichiara e tramite qualsiasi classe che eredita dalla classe padre, ma non tramite classi esterne.|
    |Protected Internal (Protected Friend in Visual Basic)|Bordo standard con quadratini di ridimensionamento: il controllo può essere ridimensionato e spostato. Accessibile internamente dalla classe che lo dichiara, da qualsiasi classe che eredita dalla classe padre e da altri membri dell'assembly che lo include.|
    |Internal (Friend in Visual Basic)|Bordo standard senza quadratini di ridimensionamento, visualizzato nel form, con proprietà visibili nella finestra **Proprietà**. Tutti gli aspetti del controllo saranno tuttavia considerati di sola lettura. Non è possibile spostare il controllo, ridimensionarlo né modificarne le proprietà. Se il controllo è un contenitore di altri controlli, come una casella di gruppo, non è possibile aggiungere nuovi controlli né rimuovere i controlli esistenti, anche in caso di controlli con livello di sicurezza Public. È possibile accedere al controllo solo tramite altri membri dell'assembly che lo contiene.|
    |Private|Bordo standard senza quadratini di ridimensionamento, visualizzato nel form, con proprietà visibili nella finestra **Proprietà**. Tutti gli aspetti del controllo saranno tuttavia considerati di sola lettura. Non è possibile spostare il controllo, ridimensionarlo né modificarne le proprietà. Se il controllo è un contenitore di altri controlli, come una casella di gruppo, non è possibile aggiungere nuovi controlli né rimuovere i controlli esistenti, anche in caso di controlli con livello di sicurezza Public. È possibile accedere al controllo solo tramite la classe che lo dichiara.|

     Per informazioni su come modificare l'aspetto di un modulo di base, vedere [Effetti della modifica dell'aspetto di un modulo di base](effects-of-modifying-base-form-appearance.md).

    > [!NOTE]
    > Quando si uniscono controlli e componenti ereditati con controlli e componenti standard in Windows Form, possono verificarsi conflitti nell'ordinamento z. È possibile correggere il problema modificando l'ordine z. Fare clic sul menu **Formato**, scegliere **Ordine** e quindi fare clic su **Porta in primo piano** o **Porta in secondo piano**. Per ulteriori informazioni sull'ordine z dei controlli, vedere [procedura: Oggetti livello su Windows Forms](../controls/how-to-layer-objects-on-windows-forms.md).

## <a name="see-also"></a>Vedere anche

- [Istruzione Inherits](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [Effetti della modifica dell'aspetto di un modulo di base](effects-of-modifying-base-form-appearance.md)
- [Ereditarietà visiva di Windows Form](windows-forms-visual-inheritance.md)
