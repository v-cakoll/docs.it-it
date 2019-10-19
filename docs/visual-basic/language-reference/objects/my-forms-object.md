---
title: Oggetto My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9a0b3b9202972122aea4a7147d8d872486418264
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581874"
---
# <a name="myforms-object"></a>Oggetto My.Forms

Fornisce le proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.

## <a name="remarks"></a>Note

L'oggetto `My.Forms` fornisce un'istanza di ogni form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà.

È possibile accedere ai moduli forniti dall'oggetto `My.Forms` usando il nome del form, senza qualifica. Poiché il nome della proprietà è uguale al nome del tipo del form, questo consente di accedere a un form come se disponesse di un'istanza predefinita. Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.

L'oggetto `My.Forms` espone solo i form associati al progetto corrente. Non fornisce l'accesso ai moduli dichiarati in dll a cui si fa riferimento. Per accedere a un modulo fornito da una DLL, è necessario utilizzare il nome completo del modulo, scritto come *dllname*. *FormName*.

È possibile usare la proprietà <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> per ottenere una raccolta di tutti i form aperti dell'applicazione.

L'oggetto e le relative proprietà sono disponibili solo per le applicazioni Windows.

## <a name="properties"></a>Proprietà

Ogni proprietà dell'oggetto `My.Forms` fornisce l'accesso a un'istanza di un form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà e il tipo della proprietà è uguale al tipo del form.

> [!NOTE]
> Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un modulo è *RootNamespace*_*namespace* \_*FormName*. Si considerino, ad esempio, due form denominati `Form1.`If uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, si accederà a tale modulo tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.

L'oggetto `My.Forms` consente di accedere all'istanza del modulo principale dell'applicazione creato all'avvio. Per tutti gli altri form, l'oggetto `My.Forms` crea una nuova istanza del form quando vi si accede e la archivia. I tentativi successivi di accesso a tale proprietà restituiscono tale istanza del form.

È possibile eliminare un form assegnando `Nothing` alla proprietà per il form. Il setter della proprietà chiama il metodo <xref:System.Windows.Forms.Form.Close%2A> del form, quindi assegna `Nothing` al valore archiviato. Se si assegna un valore diverso da `Nothing` alla proprietà, il setter genera un'eccezione <xref:System.ArgumentException>.

È possibile verificare se una proprietà dell'oggetto `My.Forms` archivia un'istanza del form utilizzando l'operatore `Is` o `IsNot`. È possibile utilizzare tali operatori per verificare se il valore della proprietà è `Nothing`.

> [!NOTE]
> In genere, l'operatore `Is` o `IsNot` deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà archivia attualmente `Nothing`, la proprietà crea una nuova istanza del form e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic considera le proprietà dell'oggetto `My.Forms` in modo diverso e consente all'operatore `Is` o `IsNot` di controllare lo stato della proprietà senza modificarne il valore.

## <a name="example"></a>Esempio

Questo esempio Mostra come modificare il titolo del modulo predefinito `SidebarMenu`.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Per il corretto funzionamento di questo esempio, il progetto deve avere un modulo denominato `SidebarMenu`.

Questo codice funzionerà solo in un progetto di applicazione Windows.

## <a name="requirements"></a>Requisiti

### <a name="availability-by-project-type"></a>Disponibilità per tipo di progetto

|Tipo di progetto|Disponibile|
|---|---|
|Applicazione Windows|**Sì**|
|Libreria di classi|No|
|Applicazione console|No|
|Libreria di controlli Windows|No|
|Libreria di controlli Web|No|
|Servizio Windows|No|
|Sito Web|No|

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [Oggetti](../../../visual-basic/language-reference/objects/index.md)
- [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Accesso ai form di un'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
