---
title: 'Procedura: Caricare e scaricare gli assembly (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
ms.openlocfilehash: efd8ddbe45323e1f80cec54379d61b5aa8a435cb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297383"
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Procedura: Caricare e scaricare gli assembly (Visual Basic)
Gli assembly cui il programma fa riferimento verranno caricati automaticamente in fase di compilazione, ma è anche possibile caricare assembly specifici nel dominio dell'applicazione corrente in fase di esecuzione. Per altre informazioni, vedere [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
 Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono. Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono.  
  
 Se si vogliono scaricare alcuni assembly ma non altri, è consigliabile creare un nuovo dominio dell'applicazione, eseguire il codice all'interno del dominio, e quindi scaricare tale dominio dell'applicazione. Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Per caricare un assembly in un dominio dell'applicazione  
  
1. Usare uno dei numerosi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e <xref:System.Reflection>. Per altre informazioni, vedere [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
### <a name="to-unload-an-application-domain"></a>Per scaricare un dominio dell'applicazione  
  
1. Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono. Per scaricare i domini dell'applicazione, usare il metodo `Unload` da <xref:System.AppDomain>. Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
## <a name="see-also"></a>Vedere anche

- [Concetti di programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](../../../../standard/assembly/index.md)
- [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
