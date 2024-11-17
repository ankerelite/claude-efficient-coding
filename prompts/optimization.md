# Guide to Creating Optimized React Artifacts for Claude

## Core Principles

1. **Aggressive Space Optimization**
- Use shortest possible variable names (e.g., 'g' for gems, 'p' for production)
- Remove all unnecessary whitespace in non-JSX code
- Use object property shorthand notation
- Minimize config object keys (e.g., 'i' for id, 'n' for name)

2. **Component Structure**
- Only extract components that will be reused multiple times
- Keep all single-use UI inline
- Use object destructuring in function parameters
- Minimize prop drilling by keeping state close to usage

3. **State Management**
- Combine related state into single objects
- Use nested state updates effectively
- Keep references stable with useCallback
- Minimize number of separate useState calls

4. **Code Organization**
```javascript
// Config objects at top, minimized
const G={U:[{i:'c',n:'Cart',c:15}]}

// Utility classes next, minimized
class P{constructor(x,y){this.x=x;this.y=y}}

// Main component last, minimized exports
export default function D(){/*...*/}
```

5. **Optimized UI Patterns**
```javascript
// Conditional rendering
{show?<div/>:null}

// Mapping with minimal syntax
{items.map(i=><div key={i.k}/>)}

// Inline styles
style={{width:'100%'}}
```

## Specific Optimization Techniques

1. **Import Optimization**
```javascript
// Instead of
import React, { useState, useEffect, useRef, useCallback } from 'react';
import { Button } from '@/components/ui/button';
import { Card, CardContent } from '@/components/ui/card';

// Use
import React,{useState,useEffect,useRef,useCallback}from'react';import{Button}from'@/components/ui/button';import{Card,CardContent}from'@/components/ui/card'
```

2. **State Structure**
```javascript
// Instead of separate states
const [gems, setGems] = useState(0)
const [production, setProduction] = useState(0)
const [upgrades, setUpgrades] = useState({})

// Use combined state
const[s,S]=useState({g:0,p:0,u:{}})
```

3. **Handler Optimization**
```javascript
// Instead of
const handleClick = useCallback((event) => {
  setState(prev => ({
    ...prev,
    gems: prev.gems + 1
  }))
}, [])

// Use 
const h=useCallback(e=>S(p=>({...p,g:p.g+1})),[])
```

## Implementation Strategy

1. Start with minimal config:
```javascript
const G={
  U:[{i:'c',n:'Cart',c:15,v:.1,m:100}],
  T:[{t:'Ruby',c:'#E31837',w:.4}]
}
```

2. Create utility classes:
```javascript
class P{
  constructor(x,y){
    this.x=x;this.y=y;this.v=0
  }
  u(){return this.v+=.1}
}
```

3. Main component structure:
```javascript
export default function D(){
  const[s,S]=useState({g:0,p:0})
  const r=useRef()
  const h=useCallback(e=>S(p=>({...p,g:p.g+1})),[])
  return(
    <div onClick={h}>
      {s.g} gems
    </div>
  )
}
```

## Key Points for LLMs

When instructing the LLM to create optimized React artifacts:

1. Direct it to:
- Use minimal variable names
- Combine similar functionality
- Remove unnecessary abstractions
- Keep code flat and efficient
- Focus on core features first

2. Remind it to:
- Test output fits in one artifact
- Maintain basic readability
- Keep code functional
- Use consistent naming
- Optimize progressively

3. Warn against:
- Creating unnecessary components
- Using lengthy variables
- Adding debug code
- Over-abstracting
- Premature optimization

The goal is to create efficient, functional code that fits within Claude's limits while remaining maintainable and extensible.
