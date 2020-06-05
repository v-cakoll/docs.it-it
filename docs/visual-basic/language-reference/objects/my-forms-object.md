---
title: Oggetto My.Forms
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 001f6fbfae2467ea0af5e98ca041b694d1e7b8f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372440"
---
# <a name="myforms-object"></a>Oggetto My.Forms

Fornisce le proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.

## <a name="remarks"></a>Commenti

L' `My.Forms` oggetto fornisce un'istanza di ogni form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà.

È possibile accedere ai moduli forniti dall' `My.Forms` oggetto utilizzando il nome del form, senza qualifica. Poiché il nome della proprietà è uguale al nome del tipo del form, questo consente di accedere a un form come se disponesse di un'istanza predefinita. Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.

L' `My.Forms` oggetto espone solo i form associati al progetto corrente. Non fornisce l'accesso ai moduli dichiarati in dll a cui si fa riferimento. Per accedere a un modulo fornito da una DLL, è necessario utilizzare il nome completo del modulo, scritto come *dllname*. *FormName*.

È possibile usare la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà per ottenere una raccolta di tutti i form aperti dell'applicazione.

L'oggetto e le relative proprietà sono disponibili solo per le applicazioni Windows.

## <a name="properties"></a>Proprietà

Ogni proprietà dell' `My.Forms` oggetto fornisce l'accesso a un'istanza di un form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà e il tipo della proprietà è uguale al tipo del form.

> [!NOTE]
> Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un modulo è *RootNamespace*_*spazio dei nomi* \_ *FormName*. Si considerino, ad esempio, due moduli denominati `Form1.` se uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1` , si accederà a tale modulo tramite `My.Forms.WindowsApplication1_Namespace1_Form1` .

L' `My.Forms` oggetto consente di accedere all'istanza del modulo principale dell'applicazione creato all'avvio. Per tutti gli altri form, l' `My.Forms` oggetto crea una nuova istanza del form quando vi si accede e la archivia. I tentativi successivi di accesso a tale proprietà restituiscono tale istanza del form.

È possibile eliminare un form assegnando `Nothing` alla proprietà per il form. Il setter della proprietà chiama il <xref:System.Windows.Forms.Form.Close%2A> metodo del form, quindi assegna il `Nothing` valore archiviato. Se si assegna un valore diverso `Nothing` da alla proprietà, il setter genera un' <xref:System.ArgumentException> eccezione.

È possibile verificare se una proprietà dell' `My.Forms` oggetto archivia un'istanza del form utilizzando l' `Is` `IsNot` operatore OR. È possibile utilizzare gli operatori per verificare se il valore della proprietà è `Nothing` .

> [!NOTE]
> In genere, `Is` l' `IsNot` operatore o deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà è attualmente archiviata `Nothing` , la proprietà crea una nuova istanza del form e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic considera le proprietà dell' `My.Forms` oggetto in modo diverso e consente `Is` all' `IsNot` operatore OR di controllare lo stato della proprietà senza modificarne il valore.

## <a name="example"></a>Esempio

In questo esempio viene modificato il titolo del `SidebarMenu` modulo predefinito.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Per il corretto funzionamento di questo esempio, il progetto deve avere un formato denominato `SidebarMenu` .

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
- [Oggetti](index.md)
- [Operatore Is](../operators/is-operator.md)
- [Operatore IsNot](../operators/isnot-operator.md)
- [Accesso ai moduli dell'applicazione](../../developing-apps/programming/accessing-application-forms.md)
