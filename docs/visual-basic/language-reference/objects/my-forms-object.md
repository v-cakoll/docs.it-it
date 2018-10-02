---
title: Oggetto My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035358"
---
# <a name="myforms-object"></a>Oggetto My.Forms
Fornisce le proprietà per l'accesso a un'istanza di ogni modulo di Windows dichiarato nel progetto corrente.  
  
## <a name="remarks"></a>Note  
 Il `My.Forms` oggetto fornisce un'istanza di ogni forma nel progetto corrente. Il nome della proprietà è identico al nome del form che accede a proprietà.   
  
 È possibile accedere ai form forniti il `My.Forms` oggetto utilizzando il nome del modulo, senza qualifica. Poiché il nome della proprietà è lo stesso nome di tipo del form, in questo modo è possibile accedere a un modulo come se avesse un'istanza predefinita. Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.  
  
 Il `My.Forms` oggetto espone solo le forme associate al progetto corrente. Non fornisce l'accesso ai moduli dichiarati nelle DLL di cui viene fatto riferimento. Per accedere a un modulo che fornisce una DLL, è necessario usare il nome completo del modulo, scritto come *DllName*. *Nomemodulo*.  
  
 È possibile usare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà da ottenere una raccolta di tutti i form aperti dell'applicazione.  
  
 L'oggetto e le relative proprietà sono disponibili solo per le applicazioni di Windows.  
  
## <a name="properties"></a>Proprietà  
 Ogni proprietà del `My.Forms` oggetto consente di accedere a un'istanza di un form nel progetto corrente. Il nome della proprietà è identico al nome del form che accede a proprietà e il tipo della proprietà è identico al tipo del form.  
  
> [!NOTE]
>  Se si verifica un conflitto di nomi, è il nome della proprietà per accedere a un form *RootNamespace*_*Namespace*\_*nomemodulo*. Ad esempio, considerare due form denominati `Form1.`se uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, è necessario accedere al form tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 Il `My.Forms` oggetto consente di accedere all'istanza del form principale dell'applicazione che è stato creato all'avvio. Per tutti gli altri moduli di `My.Forms` oggetto crea una nuova istanza del form quando si accede e archiviarli. I tentativi successivi di accedere a tale proprietà restituiscono quell'istanza del form.  
  
 È possibile rimuovere un form assegnando `Nothing` alla proprietà per tale modulo. La proprietà setter chiama il <xref:System.Windows.Forms.Form.Close%2A> metodo del form e quindi assegna `Nothing` al valore archiviato. Se si assegna un valore qualsiasi diverso da `Nothing` alla proprietà setter genera un <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà del `My.Forms` oggetto archivia un'istanza del form usando la `Is` o `IsNot` operatore. È possibile usare tali operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
>  In genere, il `Is` o `IsNot` operatore ha leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà attualmente Archivia `Nothing`, la proprietà crea una nuova istanza della forma e quindi restituisce quell'istanza. Tuttavia, il compilatore Visual Basic considera le proprietà del `My.Forms` dell'oggetto in modo diverso e consente il `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene modificato il titolo dell'oggetto default `SidebarMenu` form.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Per questo esempio funzioni, il progetto deve avere un modulo denominato `SidebarMenu`.  
  
 Questo codice funziona solo in un progetto di applicazione di Windows.  
  
## <a name="requirements"></a>Requisiti  
  
### <a name="availability-by-project-type"></a>Disponibilità dal tipo di progetto  
  
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
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Oggetti](../../../visual-basic/language-reference/objects/index.md)  
 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Accesso ai form di un'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
