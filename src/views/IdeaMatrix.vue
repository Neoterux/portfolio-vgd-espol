<template>

    <main class="flex w-full flex-col mx-auto xl:w-[75%]">
        <TitleText>Desarrollo de Videojuegos PAO-II 2023</TitleText>
        <TitleText level="2">Portafolio de Proyecto</TitleText>
        <TitleText level="3">Integrantes</TitleText>
        <ul class="max-w-md space-y-1 ps-7 mb-8 text-gray-500 list-disc list-outside items-center dark:text-gray-400">

            <li v-for="(user, index) in users" :key="index" class="align-middle">
                <div class="py-3 px-5 border-slate-200 hover:border-slate-400 hover:transition-all hover:text-slate-700 hover:font-bold hover:shadow-md dark:border-gray-800 dark:hover:text-slate-200 dark:hover:border-slate-500 border-2 rounded-lg">
                    <div class="flex items-center space-x-4">
                        <div class="flex-shrink-0">
                            <img class="w-10 h-10 rounded-full" :src="user.profile" alt="">
                        </div>
                        
                        <span class="text-xl">{{ user.name }}</span>
                    </div>
                </div>
            </li>
        </ul>
        <TitleText level="2">Tabla de Ideas</TitleText>
        

        <MatrixComponent :columns="columns" :data="data"/>
    </main>
</template>

<script setup lang="ts">
import MatrixComponent from '@/components/MatrixComponent.vue'
import TitleText from '@/components/TitleText.vue';
import { ref } from 'vue'
//https://avatars.githubusercontent.com/u/67925801?v=4

const users = [
    { profile: 'https://avatars.githubusercontent.com/u/36106785?v=4', name: 'Luis Bajaña Fernández'},
    { profile: 'https://avatars.githubusercontent.com/u/67925801?v=4', name: 'Noelia Intriago Sánchez'},
]

const columns = ref([
  'Mundos Abiertos',
  'Construcción',
  'Plataformas',
  'Estrategia',
  'Simulación',
  'Roles',
  'Toma de decisiones',
  'Competencia',
  'Cooperación',
  'Narrativa'
])

const data = ref([
  [
    'Escenario post-apocalíptico',
    'Ciudades alienígenas',
    'Cambio de gravedad en el escenario',
    'Mundo de máquinas a vapor',
    'Vida en el espacio',
    'Rol basado en texto',
    'Desarrollo de negocios',
    'Automóviles',
    'Supervivencia post-apocalíptica',
    'Héroes y villanos'
  ],
  [
    'Historia medieval',
    'Ciudades submarinas',
    'Resolución de puzzles',
    'Construcción y gestión de refugios post-apocalípticos',
    'Experiencia medieval',
    'Hackers y ciberseguridad',
    'Gestión de finanzas',
    'Equipos de fútbol',
    'Invasión alienígena',
    'Búsqueda de tesoros'
  ],
  [
    'Escenario futurista',
    'Arquitectura medieval',
    'Sincronización de música, ritmo y movimientos',
    'Monarquía y política',
    'Criaturas míticas',
    'Exploración espacial',
    'Ética y moral',
    'Deportes extremos',
    'Rescate en desastres naturales',
    'Viajes en el tiempo'
  ],
  [
    'Contexto de fantasía y magia',
    'Reconstrucción post-apocalíptica',
    'Entorno urbano',
    'Construcción de imperios',
    'Vida real',
    'Investigación forense',
    'Cirugías y hospitales',
    'Equipos tácticos',
    'Resolución de misterios',
    'Nacimiento de imperios y civilizaciones'
  ],
  [
    'Escenario ciencia ficción-realista',
    'Elaboración de materiables de construcción',
    'Escenarios inter-dimensionales',
    'Gestión de recursos en ambientes hostiles',
    'Gestión empresarial',
    'Resolución de puzzles',
    'Diagnóstico de enfermedades',
    'Ajedrez',
    'Escapar de la habitación',
    'Política'
  ],
  [
    'Historia relacionada con la mafia',
    'Construcción de vehículos',
    'Concepto de escenarios espejo o reflejos',
    'Ambientes de guerra',
    'Restaurantes',
    'Guerreros supervivientes',
    'Presidencia y política',
    'Control de territorio',
    'Experiencias paranormales',
    'Amenazas de invasión'
  ],
  [
    'Contexto cyberpunk',
    'Reconstrucción de monumentos históricos',
    'Contexto de supervivencia en ambientes hostiles',
    'Conquista espacial',
    'Guerra',
    'Exploración de lugares abandonados',
    'Resolución de crímenes',
    'Expansión de ciudades',
    'Gestión de territorios',
    'Inteligencia artificial'
  ],
  [
    'Exploración submarina',
    'Ciudades flotantes',
    'Escenario microscópico',
    'Conquista por el poder mundial',
    'Pilotaje de aviones',
    'Experiencia de terror',
    'Resolución de conflictos y guerras',
    'Carreras de obstáculos',
    'Exploración de ambientes desiertos',
    'Enfrentamiento con miedos y fobias'
  ],
  [
    'Escenario cavernícola post-extinción',
    'Construcción de defensa de ciudades',
    'Resolución de puzzles educacionales',
    'Manejo de prisiones',
    'Combate táctico',
    'Exploración del espacio exterior',
    'Elaboración de juicios',
    'Habilidades de cocina',
    'Descubrimiento de tesoros',
    'Secretos de lugares misteriosos'
  ],
  [
    'Historia de espionaje',
    'Construcción ecológica',
    'Contexto de microbiología y virus',
    'Gestión de edificios y atracciones turísticas',
    'Deporte extremo',
    'Detectives',
    'Gestión de recursos naturales',
    'Resolución de puzzles',
    'Exploración de la naturaleza',
    'Superviencia en ambientes hostiles'
  ]
])
</script>

<style >
#app {
    max-width: 100vw;
    display: flex!important;;
}

</style>
