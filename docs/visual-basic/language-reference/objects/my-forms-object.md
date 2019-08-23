---
title: Oggetto My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9fa5c77dd12c98100e3d17fc473a6802180d1e32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965975"
---
# <a name="myforms-object"></a>Oggetto My.Forms
Fornisce le proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.  
  
## <a name="remarks"></a>Note  
 L' `My.Forms` oggetto fornisce un'istanza di ogni form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà.   
  
 È possibile accedere ai moduli forniti dall' `My.Forms` oggetto utilizzando il nome del form, senza qualifica. Poiché il nome della proprietà è uguale al nome del tipo del form, questo consente di accedere a un form come se disponesse di un'istanza predefinita. Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.  
  
 L' `My.Forms` oggetto espone solo i form associati al progetto corrente. Non fornisce l'accesso ai moduli dichiarati in dll a cui si fa riferimento. Per accedere a un modulo fornito da una DLL, è necessario utilizzare il nome completo del modulo, scritto come *dllname*. *FormName*.  
  
 È possibile usare la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà per ottenere una raccolta di tutti i form aperti dell'applicazione.  
  
 L'oggetto e le relative proprietà sono disponibili solo per le applicazioni Windows.  
  
## <a name="properties"></a>Properties  
 Ogni proprietà dell' `My.Forms` oggetto fornisce l'accesso a un'istanza di un form nel progetto corrente. Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà e il tipo della proprietà è uguale al tipo del form.  
  
> [!NOTE]
> Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un modulo è *RootNamespace*_*spazio dei nomi*\_*FormName*. Si considerino, ad esempio, `Form1.`due moduli denominati se uno di questi moduli `WindowsApplication1` è nello spazio dei `Namespace1`nomi radice e nello spazio dei nomi `My.Forms.WindowsApplication1_Namespace1_Form1`, si accederà a tale modulo tramite.  
  
 L' `My.Forms` oggetto consente di accedere all'istanza del modulo principale dell'applicazione creato all'avvio. Per tutti gli altri form, `My.Forms` l'oggetto crea una nuova istanza del form quando vi si accede e la archivia. I tentativi successivi di accesso a tale proprietà restituiscono tale istanza del form.  
  
 È possibile eliminare un form assegnando `Nothing` alla proprietà per il form. Il setter della proprietà chiama <xref:System.Windows.Forms.Form.Close%2A> il metodo del form, quindi `Nothing` assegna il valore archiviato. Se si assegna un valore diverso `Nothing` da alla proprietà, il setter genera un' <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà dell' `My.Forms` oggetto archivia un'istanza del form utilizzando l' `Is` operatore OR `IsNot` . È possibile utilizzare gli operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
> In genere, `Is` l' `IsNot` operatore o deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà è attualmente `Nothing`archiviata, la proprietà crea una nuova istanza del form e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic considera le proprietà dell' `My.Forms` oggetto in modo diverso e consente all' `IsNot` `Is` operatore OR di controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene modificato il titolo del `SidebarMenu` modulo predefinito.  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 Per il corretto funzionamento di questo esempio, il progetto deve avere un `SidebarMenu`formato denominato.  
  
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
