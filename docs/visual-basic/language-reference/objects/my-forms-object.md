---
title: Oggetto My.Forms
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fe548caacf2c8e7498e3b7abc814b4f89af9b3d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="myforms-object"></a>Oggetto My.Forms
Fornisce proprietà per l'accesso a un'istanza di ogni Windows form dichiarato nel progetto corrente.  
  
## <a name="remarks"></a>Note  
 Il `My.Forms` oggetto fornisce un'istanza di ciascun form nel progetto corrente. Il nome della proprietà è identico al nome del modulo a cui accede la proprietà.   
  
 È possibile accedere ai form forniti il `My.Forms` oggetto utilizzando il nome del modulo, senza qualifica. Poiché il nome della proprietà è lo stesso nome di tipo del form, questo consente di accedere a un modulo come se disponesse di un'istanza predefinita. Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.  
  
 Il `My.Forms` oggetto espone solo il form associato al progetto corrente. Non fornisce l'accesso ai moduli dichiarati nelle DLL di cui si fa riferimento. Per accedere a un modulo che fornisce una DLL, è necessario utilizzare il nome completo del modulo, scritto come *NomeDLL*. *Nomemodulo*.  
  
 È possibile utilizzare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà da ottenere una raccolta di tutti i form aperti dell'applicazione.  
  
 L'oggetto e le relative proprietà sono disponibili solo per le applicazioni di Windows.  
  
## <a name="properties"></a>Proprietà  
 Ogni proprietà del `My.Forms` oggetto consente di accedere a un'istanza di un form nel progetto corrente. Il nome della proprietà è identico al nome del modulo che accede a proprietà e il tipo della proprietà è identico al tipo del form.  
  
> [!NOTE]
>  Se si verifica un conflitto di nome, il nome della proprietà per accedere a un modulo è *RootNamespace*_*Namespace*\_*nomemodulo*. Ad esempio, considerare due form denominati `Form1.`se uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, è possibile accedere al form tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 Il `My.Forms` oggetto consente di accedere all'istanza del form principale dell'applicazione che è stato creato all'avvio. Per tutti gli altri moduli di `My.Forms` oggetto crea una nuova istanza del modulo quando l'accesso e l'archiviazione. I tentativi successivi di accedere a questa proprietà restituiscono tale istanza del form.  
  
 Per rimuovere un modulo assegnando `Nothing` per la proprietà per tale modulo. Le chiamate di setter di proprietà di <xref:System.Windows.Forms.Form.Close%2A> metodo del form e quindi assegna `Nothing` al valore archiviato. Se si assegna un valore diverso da `Nothing` alla proprietà, il metodo set genera un <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà del `My.Forms` oggetto archivia un'istanza del form tramite il `Is` o `IsNot` operatore. È possibile utilizzare tali operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
>  In genere, il `Is` o `IsNot` operatore deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se il valore della proprietà è `Nothing`, la proprietà crea una nuova istanza del form e restituisce tale istanza. Tuttavia, il compilatore Visual Basic gestisce le proprietà del `My.Forms` dell'oggetto in modo diverso e consente la `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene modificato il titolo del valore predefinito `SidebarMenu` form.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Per eseguire questo esempio, il progetto deve disporre di un form denominato `SidebarMenu`.  
  
 Il codice funziona solo in un progetto applicazione Windows.  
  
## <a name="requirements"></a>Requisiti  
  
### <a name="availability-by-project-type"></a>Disponibilità per il tipo di progetto  
  
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
