---
title: Tipo XAML intrinseco x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053790"
---
# <a name="xcode-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:Code
Consente di posizionare il codice in una produzione XAML. Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o lasciata nell'ambiente di produzione XAML per utilizzi successivi, ad esempio l'interpretazione da parte di un Runtime.  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Note  
 Il codice all'interno `x:Code` dell'elemento di direttiva XAML viene ancora interpretato nello spazio dei nomi XML generale e negli spazi dei nomi XAML forniti. Pertanto, in genere è necessario racchiudere il codice usato per `x:Code` all'interno di un `CDATA` segmento.  
  
 `x:Code`non è consentito per tutti i meccanismi di distribuzione possibili di una produzione XAML. In Framework specifici, ad esempio WPF, è necessario compilare il codice. In altri Framework, `x:Code` l'utilizzo potrebbe essere in genere non consentito.  
  
 Per i Framework che consentono contenuto `x:Code` gestito, il compilatore di linguaggio corretto da utilizzare `x:Code` per il contenuto è determinato dalle impostazioni e dalle destinazioni del progetto contenitore utilizzato per compilare l'applicazione.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Il codice dichiarato `x:Code` in per WPF presenta diverse limitazioni rilevanti:  
  
- L' `x:Code` elemento Directive deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.  
  
- è necessario fornire la [direttiva x:Class](x-class-directive.md) sull'elemento radice padre.  
  
- Il codice inserito in `x:Code` verrà gestito dalla compilazione affinché si trovi nell'ambito della classe parziale che è già stata creata per la pagina XAML. Pertanto tutto il codice definito deve essere membro o variabili della classe parziale.  
  
- Non è possibile definire classi aggiuntive, tranne annidando una classe all'interno della classe parziale (l'annidamento è consentito, ma non è tipico perché in XAML non è possibile fare riferimento alle classi annidate). Non è possibile definire o aggiungere spazi dei nomi CLR diversi dallo spazio dei nomi usato per la classe parziale esistente.  
  
- I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR della classe parziale devono essere tutti completi. Se i membri dichiarati sono override dei membri della classe parziale sottoponibili a override, è necessario specificarli con la parola chiave di override specifica della lingua. Se i membri dichiarati nell' `x:Code` ambito sono in conflitto con i membri della classe parziale creata da XAML, in modo che il compilatore segnali il conflitto, il file XAML non può essere compilato o caricato.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Cenni preliminari su XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
