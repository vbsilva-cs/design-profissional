import { useState } from "react";

import { Button } from "@/components/ui/button";

import { Card, CardContent } from "@/components/ui/card";

import { motion } from "framer-motion";

import { Smartphone, Monitor, MessageSquare, Globe } from "lucide-react";



export default function ProjetoConectarDemo() {

&nbsp; const \[step, setStep] = useState("inicio");

&nbsp; const \[topic, setTopic] = useState(null);



&nbsp; const topics = \[

&nbsp;   { id: "mensagem", title: "Enviar mensagem", icon:  },

&nbsp;   { id: "navegar", title: "Abrir navegador", icon:  }

&nbsp; ];



&nbsp; return (

&nbsp;   



&nbsp;     

&nbsp;       Projeto Conectar – Demonstração Minimalista

&nbsp;     



&nbsp;     {step === "inicio" \&\& (

&nbsp;       

&nbsp;          setStep("topicos")} className="cursor-pointer shadow-md hover:shadow-lg transition">

&nbsp;           

&nbsp;             

&nbsp;             

Aprender no Smartphone



&nbsp;           

&nbsp;         



&nbsp;          setStep("topicos")} className="cursor-pointer shadow-md hover:shadow-lg transition">

&nbsp;           

&nbsp;             

&nbsp;             

Aprender no Computador



&nbsp;           

&nbsp;         

&nbsp;       

&nbsp;     )}



&nbsp;     {step === "topicos" \&\& (

&nbsp;       

&nbsp;         {topics.map((t) => (

&nbsp;            { setTopic(t); setStep("aprendizado"); }}

&nbsp;             className="cursor-pointer shadow-md hover:shadow-lg transition">

&nbsp;             

&nbsp;               {t.icon}

&nbsp;               

{t.title}



&nbsp;             

&nbsp;           

&nbsp;         ))}

&nbsp;       

&nbsp;     )}



&nbsp;     {step === "aprendizado" \&\& topic \&\& (

&nbsp;       

&nbsp;         

Aprendendo: {topic.title}



&nbsp;         

Demonstração rápida da tarefa...



&nbsp;         

Agora é sua vez! Tente realizar a ação.



&nbsp;          setStep("feedback")}>Concluir Atividade

&nbsp;       

&nbsp;     )}



&nbsp;     {step === "feedback" \&\& (

&nbsp;       

&nbsp;         

Parabéns!



&nbsp;         

Você concluiu a atividade e adquiriu uma nova habilidade.



&nbsp;          { setStep("topicos"); setTopic(null); }}>Voltar aos Tópicos

&nbsp;       

&nbsp;     )}

&nbsp;   



&nbsp; );

}





