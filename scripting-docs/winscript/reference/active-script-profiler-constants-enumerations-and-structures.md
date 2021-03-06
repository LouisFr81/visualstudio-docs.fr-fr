---
title: Constantes de Profiler de Script actif, énumérations et Structures | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6e079d84-9dde-46fc-8a6a-18e902f60ecc
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d367374e4402da2d30cd8a855a509299363f882
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349125"
---
# <a name="active-script-profiler-constants-enumerations-and-structures"></a>Profilage de script actif, constantes, énumérations et structures
Les énumérations suivantes sont utilisées par les Interfaces de Profiler de Script actif.  
  
## <a name="constants-enumerations-and-structures"></a>Constantes, énumérations et structures  
  
|Constantes|Description|  
|---------------|-----------------|  
|[Type PROFILER_EXTERNAL_OBJECT_ADDRESS](../../winscript/reference/profiler-external-object-address-type.md)|L’adresse de l’objet externe du profileur. Utilisé dans [profiler_heap_object, Structure](../../winscript/reference/profiler-heap-object-structure.md) et [profiler_heap_object_relationship, Structure](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[Type PROFILER_HEAP_OBJECT_ID](../../winscript/reference/profiler-heap-object-id-type.md)|ID de l’objet de tas. Utilisé dans [profiler_heap_object, Structure](../../winscript/reference/profiler-heap-object-structure.md)[profiler_heap_object_scope_list, Structure](../../winscript/reference/profiler-heap-object-scope-list-structure.md), [profiler_heap_object_optional_info, Structure](../../winscript/reference/profiler-heap-object-optional-info-structure.md)et [Profiler_heap_object_relationship, Structure](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[Type PROFILER_HEAP_OBJECT_NAME_ID](../../winscript/reference/profiler-heap-object-name-id-type.md)|L’ID du nom de l’objet de tas. Utilisé dans [profiler_heap_object, Structure](../../winscript/reference/profiler-heap-object-structure.md).|  
  
|Énumérations|Description|  
|------------------|-----------------|  
|[Énumération PROFILER_EVENT_MASK](../../winscript/reference/profiler-event-mask-enumeration.md)|Indique les types d’événements qui devraient être profilées.|  
|[Énumération PROFILER_HEAP_ENUM_FLAGS](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)|Indicateurs qui représentent si des informations supplémentaires sur un objet de tas ciblé dans une relation entre objets sont exposées. Utilisé dans le [iactivescriptprofilercontrol5::enumheap2, méthode](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md).|  
|[Énumération PROFILER_HEAP_OBJECT_FLAGS](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|Indicateurs qui représentent des informations de base sur l’objet de tas. Utilisé dans le [profiler_heap_object, Structure](../../winscript/reference/profiler-heap-object-structure.md).|  
|[Énumération PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|Représente les différents types d’informations facultatives. Utilisé dans [profiler_heap_object_optional_info, Structure](../../winscript/reference/profiler-heap-object-optional-info-structure.md).|  
|[Énumération PROFILER_RELATIONSHIP_INFO](../../winscript/reference/profiler-relationship-info-enumeration.md)|Représente des informations sur l’objet dans la relation. Utilisé dans [profiler_heap_object_relationship, Structure](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[Énumération PROFILER_SCRIPT_TYPE](../../winscript/reference/profiler-script-type-enumeration.md)|Spécifie le type de script.|  
  
|Structures|Description|  
|----------------|-----------------|  
|[Structure PROFILER_HEAP_OBJECT](../../winscript/reference/profiler-heap-object-structure.md)|Représente les objets du tas collectées par [iactivescriptprofilercontrol3::enumheap, méthode](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).|  
|[Structure PROFILER_HEAP_OBJECT_OPTIONAL_INFO ](../../winscript/reference/profiler-heap-object-optional-info-structure.md)|Représente des informations facultatives sur les objets du tas.|  
|[Structure PROFILER_HEAP_OBJECT_RELATIONSHIP](../../winscript/reference/profiler-heap-object-relationship-structure.md)|Représente une relation entre un objet de tas.|  
|[Structure PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Représente une liste de relations qui appartiennent à un objet de segment de mémoire.|  
|[Structure PROFILER_HEAP_OBJECT_SCOPE_LIST](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|Cette structure est associée à des objets de fonction uniquement. La liste étendue représente la fermeture de la fonction sous la forme d’une liste d’étendues où chaque étendue est un objet de segment de mémoire avec une liste de la propriété associée qui représente les variables dans chaque étendue donnée. Dans certains cas, les noms des objets dans cette étendue ne peuvent pas être disponibles, seulement leurs ID.|  
|[Structure PROFILER_PROPERTY_TYPE_SUBSTRING_INFO](../../winscript/reference/profiler-property-type-substring-info-structure.md)|Représente des informations sur le type de la sous-chaîne.|  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de profiler de script actif](../../winscript/reference/active-script-profiler-interfaces.md)