---
title: "Riferimento all'assembly Friend &lt;riferimento&gt; non è valido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Riferimento all'assembly Friend &lt;riferimento&gt; non è valido
Riferimento all'assembly Friend \<riferimento > non è valido. Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.  
  
 Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.  
  
 **ID errore:** BC31535  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare la chiave pubblica dell'assembly friend con nome sicuro. Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite il `PublicKey` attributo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Reflection.AssemblyName>  
 [Assembly Friend](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

