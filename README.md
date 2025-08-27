import React from "react";
import { motion } from "framer-motion";
import { CheckCircle2, ShieldCheck, Flame, Sparkles, Package, Truck, Clock, Lock, Star, ArrowRight } from "lucide-react";
// Optional shadcn/ui components (available in this environment)
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";

/**
 * 🚀 Landing page de vendas para encapsulado de emagrecimento
 * - Forte em copy e conversão
 * - Design moderno com Tailwind + Framer Motion
 * - Substitua os placeholders marcados com TODO
 */

const PRODUCT = {
  name: "SlimCaps Ultra", // TODO: nome do seu produto
  tagline: "Seca medida, aumenta energia e impulsiona sua autoestima.",
  checkoutUrl: "https://seu-checkout.com/pagamento", // TODO: link do checkout
  supportEmail: "suporte@seudominio.com", // TODO
};

const bundles = [
  {
    id: "kit3",
    title: "Kit Transformação (3 Potes)",
    highlight: "Mais vendido",
    price: "R$ 297",
    per: "R$ 99 por pote",
    bullets: [
      "Resultados acelerados",
      "Frete grátis Brasil",
      "Acompanhamento por e‑mail",
    ],
    save: "Economize 35%",
  },
  {
    id: "kit1",
    title: "Iniciante (1 Pote)",
    highlight: "Teste rápido",
    price: "R$ 129",
    per: "30 doses",
    bullets: ["Energia e saciedade", "Entrega rápida", "Compra segura"],
    save: "Preço de entrada",
  },
  {
    id: "kit5",
    title: "Resultados Máximos (5 Potes)",
    highlight: "Maior desconto",
    price: "R$ 445",
    per: "R$ 89 por pote",
    bullets: [
      "Plano completo de 150 dias",
      "Frete + brinde",
      "Economia máxima",
    ],
    save: "Economize 45%",
  },
];

const benefits = [
  { icon: Flame, title: "Acelera o metabolismo", text: "Potencializa a queima de gordura ao longo do dia." },
  { icon: Sparkles, title: "Reduz o apetite", text: "Ajuda a controlar a compulsão e o beliscar." },
  { icon: Package, title: "Fórmula concentrada", text: "Blend exclusivo de ativos de origem natural." },
  { icon: Clock, title: "Rotina simples", text: "1–2 cápsulas ao dia, sem complicação." },
];

const faqs = [
  {
    q: "Em quanto tempo vejo resultados?",
    a: "Muitas pessoas relatam mudanças nas primeiras semanas. Resultados variam conforme rotina, alimentação e individualidade biológica.",
  },
  {
    q: "Como devo tomar?",
    a: "Sugerimos 1 cápsula 2x ao dia, 30 minutos antes das principais refeições, com água. Sempre siga as instruções do rótulo.",
  },
  {
    q: "Tem contraindicações?",
    a: "Gestantes, lactantes, crianças e pessoas com condições específicas devem consultar profissional de saúde antes do uso.",
  },
  {
    q: "É medicamento?",
    a: "Não. É um suplemento nutricional. Não substitui uma alimentação equilibrada e hábitos saudáveis.",
  },
];

export default function LandingPage() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-white to-slate-50 text-slate-900">
      {/* Header */}
      <header className="sticky top-0 z-40 backdrop-blur bg-white/70 border-b border-slate-200">
        <div className="max-w-6xl mx-auto px-4 py-3 flex items-center justify-between">
          <div className="flex items-center gap-2">
            <div className="h-8 w-8 rounded-xl bg-slate-900 text-white grid place-items-center font-bold">S</div>
            <span className="font-semibold">{PRODUCT.name}</span>
          </div>
          <div className="hidden md:flex items-center gap-6 text-sm">
            <a href="#beneficios" className="hover:text-slate-600">Benefícios</a>
            <a href="#como-funciona" className="hover:text-slate-600">Como funciona</a>
            <a href="#oferta" className="hover:text-slate-600">Ofertas</a>
            <a href="#faq" className="hover:text-slate-600">Dúvidas</a>
          </div>
          <a href={PRODUCT.checkoutUrl} className="inline-flex items-center gap-2 rounded-2xl px-4 py-2 bg-slate-900 text-white hover:opacity-90 transition">
            Comprar agora <ArrowRight className="h-4 w-4" />
          </a>
        </div>
      </header>

      {/* Hero */}
      <section className="relative overflow-hidden">
        <div className="max-w-6xl mx-auto px-4 py-20 grid md:grid-cols-2 gap-10 items-center">
          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
            <h1 className="text-4xl md:text-5xl font-extrabold leading-tight">
              Emagreça com confiança: <span className="text-slate-700">resultado que você vê no espelho</span>
            </h1>
            <p className="mt-4 text-lg text-slate-600">
              {PRODUCT.tagline} Desenvolvido para apoiar a perda de peso de forma prática e inteligente, aliado a uma rotina real e possível.
            </p>
            <ul className="mt-6 space-y-3 text-slate-700">
              {[
                "Queima calórica potencializada ao longo do dia",
                "Apoio à saciedade e ao controle do apetite",
                "Energia e foco para manter a constância",
              ].map((t, i) => (
                <li key={i} className="flex items-center gap-3"><CheckCircle2 className="h-5 w-5" /> {t}</li>
              ))}
            </ul>
            <div className="mt-8 flex flex-wrap items-center gap-3">
              <Button asChild className="rounded-2xl px-6 py-6 text-base">
                <a href={PRODUCT.checkoutUrl}>Quero Começar Hoje</a>
              </Button>
              <div className="flex items-center gap-2 text-sm text-slate-500">
                <ShieldCheck className="h-4 w-4" /> Compra 100% segura
              </div>
            </div>
            <p className="mt-3 text-xs text-slate-500">*Resultados variam. Suplemento não é medicamento. Consulte profissional de saúde.**</p>
          </motion.div>

          <motion.div initial={{ opacity: 0, scale: 0.98 }} animate={{ opacity: 1, scale: 1 }} transition={{ duration: 0.6, delay: 0.1 }}>
            <Card className="rounded-3xl shadow-xl border-slate-200">
              <CardContent className="p-6">
                <div className="aspect-[4/3] w-full rounded-2xl bg-gradient-to-br from-slate-100 to-slate-200 grid place-items-center">
                  <div className="text-center">
                    <div className="text-sm uppercase tracking-wider text-slate-500">Imagem do Produto</div>
                    <div className="mt-1 text-xs text-slate-500">Substitua por foto real do frasco</div>
                  </div>
                </div>
                <div className="mt-4 grid grid-cols-3 gap-3 text-center text-sm">
                  {[
                    { icon: Truck, label: "Frete rápido" },
                    { icon: Lock, label: "Checkout criptografado" },
                    { icon: Star, label: "Satisfação garantida" },
                  ].map((b, i) => (
                    <div key={i} className="rounded-2xl border border-slate-200 p-3 flex flex-col items-center gap-2">
                      <b.icon className="h-5 w-5" />
                      <span>{b.label}</span>
                    </div>
                  ))}
                </div>
              </CardContent>
            </Card>
          </motion.div>
        </div>
      </section>

      {/* Benefícios */}
      <section id="beneficios" className="py-14 bg-white">
        <div className="max-w-6xl mx-auto px-4">
          <h2 className="text-3xl font-bold">Por que {PRODUCT.name} funciona no seu dia a dia</h2>
          <p className="mt-2 text-slate-600">Foco em três pilares: metabolismo, saciedade e energia.</p>
          <div className="mt-8 grid sm:grid-cols-2 lg:grid-cols-4 gap-5">
            {benefits.map((b, i) => (
              <motion.div key={i} initial={{ opacity: 0, y: 12 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ duration: 0.4, delay: i * 0.05 }} className="rounded-3xl border border-slate-200 p-6 bg-slate-50">
                <b.icon className="h-6 w-6" />
                <h3 className="mt-3 font-semibold">{b.title}</h3>
                <p className="text-slate-600 text-sm mt-1">{b.text}</p>
              </motion.div>
            ))}
          </div>
        </div>
      </section>

      {/* Como funciona / Ciência simples */}
      <section id="como-funciona" className="py-16 bg-slate-50">
        <div className="max-w-6xl mx-auto px-4 grid lg:grid-cols-2 gap-10 items-start">
          <div>
            <h2 className="text-3xl font-bold">Simples, prático e pensado para constância</h2>
            <p className="mt-3 text-slate-600">
              Uma combinação estratégica de ingredientes de origem natural, como termogênicos e fibras, que apoiam o gasto calórico e a sensação de saciedade. Use diariamente e acompanhe sua evolução.
            </p>
            <ul className="mt-6 space-y-3 text-slate-700">
              {[
                "1–2 cápsulas por dia com água",
                "Alie a uma alimentação equilibrada",
                "Movimente-se (caminhada já ajuda)",
                "Beba água e durma bem",
              ].map((t, i) => (
                <li key={i} className="flex items-center gap-3"><CheckCircle2 className="h-5 w-5" /> {t}</li>
              ))}
            </ul>
          </div>
          <div>
            <Card className="rounded-3xl border-slate-200">
              <CardContent className="p-6">
                <h3 className="font-semibold">Diferenciais</h3>
                <div className="mt-4 grid sm:grid-cols-2 gap-4">
                  {[
                    { title: "Fórmula limpa", text: "Sem açúcares adicionados e sem glúten." },
                    { title: "Rótulo transparente", text: "Sem promessas milagrosas: consistência vence." },
                    { title: "Feito no Brasil", text: "Boas práticas de fabricação e controle." },
                    { title: "Garantia 30 dias", text: "Satisfeito ou reembolso simples." },
                  ].map((x, i) => (
                    <div key={i} className="rounded-2xl bg-white border border-slate-200 p-4">
                      <h4 className="font-medium">{x.title}</h4>
                      <p className="text-sm text-slate-600 mt-1">{x.text}</p>
                    </div>
                  ))}
                </div>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* Prova social */}
      <section className="py-16 bg-white">
        <div className="max-w-6xl mx-auto px-4">
          <h2 className="text-3xl font-bold">Histórias reais de motivação</h2>
          <p className="mt-2 text-slate-600">Depoimentos ilustrativos de clientes que adotaram uma rotina saudável com o suplemento.</p>
          <div className="mt-8 grid md:grid-cols-3 gap-5">
            {[1,2,3].map((i) => (
              <Card key={i} className="rounded-3xl border-slate-200">
                <CardContent className="p-6">
                  <div className="flex items-center gap-3">
                    <div className="h-10 w-10 rounded-full bg-slate-200" />
                    <div>
                      <div className="font-semibold">Cliente {i}</div>
                      <div className="text-xs text-slate-500">Uso contínuo</div>
                    </div>
                  </div>
                  <p className="mt-4 text-sm text-slate-700">
                    “Me senti com mais energia e controle da fome nas primeiras semanas. Mantendo a rotina, vi meu corpo responder dia após dia.”
                  </p>
                  <div className="mt-4 flex items-center gap-1 text-amber-500">
                    {[...Array(5)].map((_, idx) => (<Star key={idx} className="h-4 w-4 fill-current" />))}
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Oferta */}
      <section id="oferta" className="py-18 bg-slate-50">
        <div className="max-w-6xl mx-auto px-4">
          <h2 className="text-3xl font-bold">Escolha seu kit e comece agora</h2>
          <p className="mt-2 text-slate-600">Oferta exclusiva online. Estoque limitado.</p>
          <div className="mt-8 grid lg:grid-cols-3 gap-6">
            {bundles.map((b, i) => (
              <motion.div key={b.id} initial={{ opacity: 0, y: 10 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ duration: 0.4, delay: i * 0.05 }} className="relative">
                <Card className={`rounded-3xl border-2 ${b.id === "kit3" ? "border-slate-900" : "border-slate-200"}`}>
                  <CardContent className="p-6">
                    <div className="flex items-center justify-between">
                      <h3 className="text-xl font-semibold">{b.title}</h3>
                      <span className="text-xs px-2 py-1 rounded-full bg-slate-900 text-white">{b.highlight}</span>
                    </div>
                    <div className="mt-3 text-3xl font-extrabold">{b.price}</div>
                    <div className="text-slate-500 text-sm">{b.per}</div>
                    <ul className="mt-4 space-y-2 text-sm">
                      {b.bullets.map((x, idx) => (
                        <li key={idx} className="flex items-center gap-2"><CheckCircle2 className="h-4 w-4" /> {x}</li>
                      ))}
                    </ul>
                    <div className="mt-4 text-xs text-emerald-700 font-medium">{b.save}</div>
                    <Button asChild className="mt-6 w-full rounded-2xl py-6 text-base">
                      <a href={PRODUCT.checkoutUrl}>Quero este kit</a>
                    </Button>
                  </CardContent>
                </Card>
              </motion.div>
            ))}
          </div>
          <div className="mt-6 text-center text-sm text-slate-500">Pagamento em até 12x no cartão | Pix e Boleto disponíveis</div>
        </div>
      </section>

      {/* Garantia */}
      <section className="py-16 bg-white">
        <div className="max-w-4xl mx-auto px-4">
          <Card className="rounded-3xl border-slate-200">
            <CardContent className="p-6 md:p-10 grid md:grid-cols-5 gap-6 items-center">
              <div className="md:col-span-1">
                <ShieldCheck className="h-12 w-12" />
              </div>
              <div className="md:col-span-4">
                <h3 className="text-2xl font-bold">Garantia de Satisfação de 30 Dias</h3>
                <p className="mt-2 text-slate-600">
                  Experimente sem medo. Se não ficar satisfeito em até 30 dias, devolvemos 100% do seu investimento. Simples, seguro e sem burocracia.
                </p>
              </div>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* FAQ */}
      <section id="faq" className="py-16 bg-slate-50">
        <div className="max-w-4xl mx-auto px-4">
          <h2 className="text-3xl font-bold">Dúvidas Frequentes</h2>
          <div className="mt-6 divide-y divide-slate-200 rounded-3xl border border-slate-200 bg-white">
            {faqs.map((f, i) => (
              <details key={i} className="group p-6">
                <summary className="cursor-pointer list-none font-medium flex items-center justify-between">
                  {f.q}
                  <span className="ml-4 text-slate-400 group-open:rotate-90 transition">›</span>
                </summary>
                <p className="mt-3 text-slate-600">{f.a}</p>
              </details>
            ))}
          </div>
          <p className="mt-4 text-xs text-slate-500">
            Aviso legal: {PRODUCT.name} é um suplemento alimentar. Não é destinado a diagnosticar, tratar, curar ou prevenir doenças. Resultados variam conforme indivíduo.
          </p>
        </div>
      </section>

      {/* CTA final */}
      <section className="py-16 bg-gradient-to-b from-slate-900 to-slate-800 text-white">
        <div className="max-w-6xl mx-auto px-4 grid md:grid-cols-2 gap-8 items-center">
          <div>
            <h2 className="text-3xl font-extrabold">Comece hoje. O melhor momento é agora.</h2>
            <p className="mt-3 text-slate-300">Coloque sua saúde no topo da lista e dê o primeiro passo com {PRODUCT.name}.</p>
          </div>
          <div className="flex md:justify-end">
            <a href={PRODUCT.checkoutUrl} className="inline-flex items-center gap-2 rounded-2xl bg-white text-slate-900 px-6 py-4 hover:opacity-90">
              Garantir meu kit <ArrowRight className="h-5 w-5" />
            </a>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-10 bg-white border-t border-slate-200 text-sm">
        <div className="max-w-6xl mx-auto px-4 flex flex-col md:flex-row items-center justify-between gap-4">
          <div className="text-slate-500">© {new Date().getFullYear()} {PRODUCT.name}. Todos os direitos reservados.</div>
          <div className="text-slate-500 flex items-center gap-4">
            <a href="#" className="hover:text-slate-700">Política de Privacidade</a>
            <a href="#" className="hover:text-slate-700">Termos de Uso</a>
            <a href={`mailto:${PRODUCT.supportEmail}`} className="hover:text-slate-700">Suporte</a>
          </div>
        </div>
      </footer>
    </div>
  );
}

