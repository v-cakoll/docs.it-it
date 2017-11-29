---
title: 'Procedura: condividere un Assembly con altre applicazioni (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 491791ba9b6f0cf6da86a160eddf8e78109b11c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Procedura: condividere un Assembly con altre applicazioni (Visual Basic)
Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.  
  
 Per condividerlo con altre applicazioni, un assembly deve essere inserito nella [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Condivisione di un assembly  
  
1.  Creare l'assembly. Per altre informazioni, vedere [Creazione degli assembly](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Assegnare all'assembly un nome sicuro. Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Assegnare all'assembly le informazioni sulla versione. Per altre informazioni, vedere [Controllo delle versioni degli assembly](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Aggiungere l'assembly alla Global Assembly Cache. Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Accedere ai tipi contenuti nell'assembly da altre applicazioni. Per altre informazioni, vedere [Procedura: Aggiungere un riferimento a un assembly con nome sicuro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti relativi alla programmazione](../../../../visual-basic/programming-guide/concepts/index.md) [assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Programmazione con gli assembly](../../../../framework/app-domains/programming-with-assemblies.md)
