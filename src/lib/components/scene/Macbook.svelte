<script lang="ts">
    import type * as THREE from 'three';
    import {Group, MeshBasicMaterial} from 'three';
    import {T, type Props, type Events, type Slots, forwardEventHandlers, useLoader} from '@threlte/core';
    import {useGltf, useSuspense, useTexture} from '@threlte/extras';

    type $$Props = Props<THREE.Group> & {scroll: number; screenSrc: string};
    type $$Events = Events<THREE.Group>;
    type $$Slots = Slots<THREE.Group> & {fallback: {}; error: {error: any}};

    export let scroll: number;
    export let screenSrc: string;

    export const ref = new Group();

    const suspend = useSuspense();

    type GLTFResult = {
        nodes: {
            WDUVUVPpNjdIPkb: THREE.Mesh;
            NqUinIWcwSlXpvt: THREE.Mesh;
            MaufYfIBnxcfRgH: THREE.Mesh;
            aIqeGXayDxWnOWQ: THREE.Mesh;
            xVreGKoBGSZYMij: THREE.Mesh;
            CTBERffHyoCSDBm_0: THREE.Mesh;
            hczGzWOWpedUDYd_0: THREE.Mesh;
            biHEvGDNnTqamRb: THREE.Mesh;
            TyOrApjEOLhYCaF: THREE.Mesh;
            vrIckaCELZpnnNK: THREE.Mesh;
            SadnAkehSlxIwKv: THREE.Mesh;
            OrhpMXCxeprcNok: THREE.Mesh;
            aLWGnOLpsFWVSfy: THREE.Mesh;
            ACMWKGtOCqXifQY: THREE.Mesh;
            BkHyotPbPWzwAAj: THREE.Mesh;
            bkcxDtALZjuqGGQ: THREE.Mesh;
            rktWdhtZkCSmqne: THREE.Mesh;
            hztTkkTJBJTZDmk: THREE.Mesh;
            bHBjPHbrqJmhyoR: THREE.Mesh;
            HHcJitDCPTdgnFk: THREE.Mesh;
            DRGkWmkJlgmNDJU: THREE.Mesh;
            KMwpdMtieDqmHVU: THREE.Mesh;
            KgPDMIRPrxAynTV: THREE.Mesh;
            XwGJfoaIrduFPcU: THREE.Mesh;
            znOBoeqnOAcWvld: THREE.Mesh;
            ebZHPVwKTmqvgbU: THREE.Mesh;
            uSnVzUkbvcGaVtm: THREE.Mesh;
            tIZmzvOOHrlOFci: THREE.Mesh;
            UmfOhraHkqkMHJr: THREE.Mesh;
            roXkINNmErodbSy: THREE.Mesh;
            wWWhLQmmNVhThGV: THREE.Mesh;
            JoRHkRchuIHZFdI: THREE.Mesh;
            qJLFXXZhlqhKvcM: THREE.Mesh;
            thJvyyEdPZIkQGr: THREE.Mesh;
            juMIjHdkYweLlGP: THREE.Mesh;
            zNYAavJLMZZchIX: THREE.Mesh;
            bzbXKgxvWZbXAqu: THREE.Mesh;
            guzkNjLPdYYIFbm: THREE.Mesh;
            CkZgGMshUOhytMM: THREE.Mesh;
            oiLbjgjnUUhPosp: THREE.Mesh;
            nDWhlgWONddUcnN: THREE.Mesh;
            HrtjMXqDCcINmDE_0: THREE.Mesh;
            zWqVyCKpTAuZNiu_0: THREE.Mesh;
            MYVKQTLmUkzzlBj_0: THREE.Mesh;
            qEJjkxdFZFWJWzR_0: THREE.Mesh;
            lvlCIzdfTmsrnsM: THREE.Mesh;
            eeWSraIVipLsSmX_0: THREE.Mesh;
            PgbYkhvRdcmMeGL: THREE.Mesh;
            VAcTKRVsYcEMWxB: THREE.Mesh;
        };
        materials: {
            ZPlxrBOYjSNYvVB: THREE.MeshStandardMaterial;
            rvYnnyqXrbFJXxh: THREE.MeshStandardMaterial;
            SsSIPrCyVNTOxvd: THREE.MeshStandardMaterial;
            dkOmcmuFedorUKC: THREE.MeshStandardMaterial;
            dKLyhhkbEyMrqky: THREE.MeshStandardMaterial;
            YjmXmicdBWsFQyD: THREE.MeshStandardMaterial;
            pEUnNAGXCoAFoUk: THREE.MeshStandardMaterial;
            dFfswgailNMtaYj: THREE.MeshStandardMaterial;
            AZirwHJdxxcChtp: THREE.MeshStandardMaterial;
            VNZklasZKSWjWUk: THREE.MeshStandardMaterial;
            OfvrpEsWzbOpbcs: THREE.MeshStandardMaterial;
            iFCKstMLETFqCmZ: THREE.MeshStandardMaterial;
            RMDHOHZakhhXXHT: THREE.MeshStandardMaterial;
            sRPrqogRtliLLae: THREE.MeshStandardMaterial;
            ZrrjpMZNDbttBCc: THREE.MeshStandardMaterial;
            hZBlDyddxAQhuPm: THREE.MeshStandardMaterial;
            kDpbvvjwMgCSCmF: THREE.MeshStandardMaterial;
            AqVxlXuHIFahLKs: THREE.MeshStandardMaterial;
            oKQWdLrXUCbYByI: THREE.MeshStandardMaterial;
            OFvWomWIIUgmKKA: THREE.MeshStandardMaterial;
            mEMAJQfiigHeUXV: THREE.MeshStandardMaterial;
            NzmRSNqyvNKhkmK: THREE.MeshStandardMaterial;
            ASadxrcBIAXFnLn: THREE.MeshStandardMaterial;
            JKvAHnqjqlqshmY: THREE.MeshStandardMaterial;
            AvocVUvikCzzMtu: THREE.MeshStandardMaterial;
            wOIDWopwzKBeTNU: THREE.MeshStandardMaterial;
            BfIgIOaUEgyoEft: THREE.MeshStandardMaterial;
            zFJMMvikHFjtmzd: THREE.MeshStandardMaterial;
            jIhmcgKbjDOICsY: THREE.MeshStandardMaterial;
        };
    };

    const gltf = suspend(useGltf<GLTFResult>('/macbook.glb', {useDraco: true}));

    $: screenMap = useTexture(screenSrc);
    const debugMat = new MeshBasicMaterial({color: 'magenta'});
    const component = forwardEventHandlers();
</script>

<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
    {#await gltf}
        <slot name="fallback" />
    {:then gltf}
        <T.Group name="USDRoot" scale={0.04} position.z={scroll < 0.8 ? 0 : (scroll - 0.8) * -100} rotation.x={0.2} rotation.y={scroll * 32}>
            <T.Mesh name="xVreGKoBGSZYMij" castShadow receiveShadow geometry={gltf.nodes.xVreGKoBGSZYMij.geometry} material={gltf.materials.dKLyhhkbEyMrqky} />
            <T.Mesh
                name="CTBERffHyoCSDBm_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.CTBERffHyoCSDBm_0.geometry}
                material={gltf.materials.YjmXmicdBWsFQyD}
            />
            <T.Mesh
                name="hczGzWOWpedUDYd_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.hczGzWOWpedUDYd_0.geometry}
                material={gltf.materials.pEUnNAGXCoAFoUk}
            />
            <T.Mesh name="Screen" castShadow receiveShadow geometry={gltf.nodes.SadnAkehSlxIwKv.geometry}>
                {#if $screenMap}
                    <T.MeshPhysicalMaterial map={$screenMap} roughness={0} metalness={0.2} />
                {:else}
                    <T.MeshPhysicalMaterial color="#555555" metalness={0.8} />
                {/if}
            </T.Mesh>
            <T.Mesh name="biHEvGDNnTqamRb" castShadow receiveShadow geometry={gltf.nodes.biHEvGDNnTqamRb.geometry} material={gltf.materials.dFfswgailNMtaYj} />
            <T.Mesh name="TyOrApjEOLhYCaF" castShadow receiveShadow geometry={gltf.nodes.TyOrApjEOLhYCaF.geometry} material={gltf.materials.AZirwHJdxxcChtp} />
            <T.Mesh name="vrIckaCELZpnnNK" castShadow receiveShadow geometry={gltf.nodes.vrIckaCELZpnnNK.geometry} material={gltf.materials.dkOmcmuFedorUKC} />
            <T.Mesh name="OrhpMXCxeprcNok" castShadow receiveShadow geometry={gltf.nodes.OrhpMXCxeprcNok.geometry} material={gltf.materials.OfvrpEsWzbOpbcs} />
            <T.Mesh name="aLWGnOLpsFWVSfy" castShadow receiveShadow geometry={gltf.nodes.aLWGnOLpsFWVSfy.geometry} material={gltf.materials.iFCKstMLETFqCmZ} />
            <T.Mesh name="WDUVUVPpNjdIPkb" castShadow receiveShadow geometry={gltf.nodes.WDUVUVPpNjdIPkb.geometry} material={gltf.materials.ZPlxrBOYjSNYvVB} />
            <T.Mesh name="NqUinIWcwSlXpvt" castShadow receiveShadow geometry={gltf.nodes.NqUinIWcwSlXpvt.geometry} material={gltf.materials.rvYnnyqXrbFJXxh} />
            <T.Mesh name="MaufYfIBnxcfRgH" castShadow receiveShadow geometry={gltf.nodes.MaufYfIBnxcfRgH.geometry} material={gltf.materials.SsSIPrCyVNTOxvd} />
            <T.Mesh name="aIqeGXayDxWnOWQ" castShadow receiveShadow geometry={gltf.nodes.aIqeGXayDxWnOWQ.geometry} material={gltf.materials.dkOmcmuFedorUKC} />
            <T.Mesh
                name="HrtjMXqDCcINmDE_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.HrtjMXqDCcINmDE_0.geometry}
                material={gltf.materials.BfIgIOaUEgyoEft}
            />
            <T.Mesh
                name="zWqVyCKpTAuZNiu_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.zWqVyCKpTAuZNiu_0.geometry}
                material={gltf.materials.zFJMMvikHFjtmzd}
            />
            <T.Mesh
                name="MYVKQTLmUkzzlBj_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.MYVKQTLmUkzzlBj_0.geometry}
                material={gltf.materials.jIhmcgKbjDOICsY}
            />
            <T.Mesh
                name="qEJjkxdFZFWJWzR_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.qEJjkxdFZFWJWzR_0.geometry}
                material={gltf.materials.JKvAHnqjqlqshmY}
            />
            <T.Mesh name="lvlCIzdfTmsrnsM" castShadow receiveShadow geometry={gltf.nodes.lvlCIzdfTmsrnsM.geometry} material={gltf.materials.iFCKstMLETFqCmZ} />
            <T.Mesh
                name="eeWSraIVipLsSmX_0"
                castShadow
                receiveShadow
                geometry={gltf.nodes.eeWSraIVipLsSmX_0.geometry}
                material={gltf.materials.JKvAHnqjqlqshmY}
            />
            <T.Mesh name="PgbYkhvRdcmMeGL" castShadow receiveShadow geometry={gltf.nodes.PgbYkhvRdcmMeGL.geometry} material={gltf.materials.wOIDWopwzKBeTNU} />
            <T.Mesh name="rktWdhtZkCSmqne" castShadow receiveShadow geometry={gltf.nodes.rktWdhtZkCSmqne.geometry} material={gltf.materials.ZrrjpMZNDbttBCc} />
            <T.Mesh name="hztTkkTJBJTZDmk" castShadow receiveShadow geometry={gltf.nodes.hztTkkTJBJTZDmk.geometry} material={gltf.materials.ZrrjpMZNDbttBCc} />
            <T.Mesh name="bHBjPHbrqJmhyoR" castShadow receiveShadow geometry={gltf.nodes.bHBjPHbrqJmhyoR.geometry} material={gltf.materials.ZrrjpMZNDbttBCc} />
            <T.Mesh name="HHcJitDCPTdgnFk" castShadow receiveShadow geometry={gltf.nodes.HHcJitDCPTdgnFk.geometry} material={gltf.materials.RMDHOHZakhhXXHT} />
            <T.Mesh name="DRGkWmkJlgmNDJU" castShadow receiveShadow geometry={gltf.nodes.DRGkWmkJlgmNDJU.geometry} material={gltf.materials.RMDHOHZakhhXXHT} />
            <T.Mesh name="KMwpdMtieDqmHVU" castShadow receiveShadow geometry={gltf.nodes.KMwpdMtieDqmHVU.geometry} material={gltf.materials.RMDHOHZakhhXXHT} />
            <T.Mesh name="KgPDMIRPrxAynTV" castShadow receiveShadow geometry={gltf.nodes.KgPDMIRPrxAynTV.geometry} material={gltf.materials.hZBlDyddxAQhuPm} />
            <T.Mesh name="XwGJfoaIrduFPcU" castShadow receiveShadow geometry={gltf.nodes.XwGJfoaIrduFPcU.geometry} material={gltf.materials.YjmXmicdBWsFQyD} />
            <T.Mesh name="ACMWKGtOCqXifQY" castShadow receiveShadow geometry={gltf.nodes.ACMWKGtOCqXifQY.geometry} material={gltf.materials.RMDHOHZakhhXXHT} />
            <T.Mesh name="BkHyotPbPWzwAAj" castShadow receiveShadow geometry={gltf.nodes.BkHyotPbPWzwAAj.geometry} material={gltf.materials.sRPrqogRtliLLae} />
            <T.Mesh name="bkcxDtALZjuqGGQ" castShadow receiveShadow geometry={gltf.nodes.bkcxDtALZjuqGGQ.geometry} material={gltf.materials.RMDHOHZakhhXXHT} />
            <T.Mesh name="ebZHPVwKTmqvgbU" castShadow receiveShadow geometry={gltf.nodes.ebZHPVwKTmqvgbU.geometry} material={gltf.materials.kDpbvvjwMgCSCmF} />
            <T.Mesh name="uSnVzUkbvcGaVtm" castShadow receiveShadow geometry={gltf.nodes.uSnVzUkbvcGaVtm.geometry} material={gltf.materials.AqVxlXuHIFahLKs} />
            <T.Mesh name="znOBoeqnOAcWvld" castShadow receiveShadow geometry={gltf.nodes.znOBoeqnOAcWvld.geometry} material={gltf.materials.dKLyhhkbEyMrqky} />
            <T.Mesh name="tIZmzvOOHrlOFci" castShadow receiveShadow geometry={gltf.nodes.tIZmzvOOHrlOFci.geometry} material={gltf.materials.oKQWdLrXUCbYByI} />
            <T.Mesh name="UmfOhraHkqkMHJr" castShadow receiveShadow geometry={gltf.nodes.UmfOhraHkqkMHJr.geometry} material={gltf.materials.OFvWomWIIUgmKKA} />
            <T.Mesh name="roXkINNmErodbSy" castShadow receiveShadow geometry={gltf.nodes.roXkINNmErodbSy.geometry} material={gltf.materials.oKQWdLrXUCbYByI} />
            <T.Mesh name="wWWhLQmmNVhThGV" castShadow receiveShadow geometry={gltf.nodes.wWWhLQmmNVhThGV.geometry} material={gltf.materials.OFvWomWIIUgmKKA} />
            <T.Mesh name="JoRHkRchuIHZFdI" castShadow receiveShadow geometry={gltf.nodes.JoRHkRchuIHZFdI.geometry} material={gltf.materials.mEMAJQfiigHeUXV} />
            <T.Mesh name="qJLFXXZhlqhKvcM" castShadow receiveShadow geometry={gltf.nodes.qJLFXXZhlqhKvcM.geometry} material={gltf.materials.mEMAJQfiigHeUXV} />
            <T.Mesh name="thJvyyEdPZIkQGr" castShadow receiveShadow geometry={gltf.nodes.thJvyyEdPZIkQGr.geometry} material={gltf.materials.OFvWomWIIUgmKKA} />
            <T.Mesh name="juMIjHdkYweLlGP" castShadow receiveShadow geometry={gltf.nodes.juMIjHdkYweLlGP.geometry} material={gltf.materials.NzmRSNqyvNKhkmK} />
            <T.Mesh name="zNYAavJLMZZchIX" castShadow receiveShadow geometry={gltf.nodes.zNYAavJLMZZchIX.geometry} material={gltf.materials.ASadxrcBIAXFnLn} />
            <T.Mesh name="bzbXKgxvWZbXAqu" castShadow receiveShadow geometry={gltf.nodes.bzbXKgxvWZbXAqu.geometry} material={gltf.materials.JKvAHnqjqlqshmY} />
            <T.Mesh name="guzkNjLPdYYIFbm" castShadow receiveShadow geometry={gltf.nodes.guzkNjLPdYYIFbm.geometry} material={gltf.materials.dkOmcmuFedorUKC} />
            <T.Mesh name="CkZgGMshUOhytMM" castShadow receiveShadow geometry={gltf.nodes.CkZgGMshUOhytMM.geometry} material={gltf.materials.AvocVUvikCzzMtu} />
            <T.Mesh name="oiLbjgjnUUhPosp" castShadow receiveShadow geometry={gltf.nodes.oiLbjgjnUUhPosp.geometry} material={gltf.materials.AvocVUvikCzzMtu} />
            <T.Mesh name="nDWhlgWONddUcnN" castShadow receiveShadow geometry={gltf.nodes.nDWhlgWONddUcnN.geometry} material={gltf.materials.wOIDWopwzKBeTNU} />
            <T.Mesh name="VAcTKRVsYcEMWxB" castShadow receiveShadow geometry={gltf.nodes.VAcTKRVsYcEMWxB.geometry} material={gltf.materials.dkOmcmuFedorUKC} />
        </T.Group>
    {:catch error}
        <slot name="error" {error} />
    {/await}

    <slot {ref} />
</T>
